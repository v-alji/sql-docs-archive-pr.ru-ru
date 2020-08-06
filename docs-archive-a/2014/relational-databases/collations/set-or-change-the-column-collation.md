---
title: Установка и изменение параметров сортировки для столбца | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
helpviewer_keywords:
- tempdb database [SQL Server], collations
- collations [SQL Server], column
ms.assetid: d7a9638b-717c-4680-9b98-8849081e08be
author: stevestein
ms.author: sstein
ms.openlocfilehash: 05b8211569b6ce83faaec043e5eb527a60f0ddab
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87668917"
---
# <a name="set-or-change-the-column-collation"></a><span data-ttu-id="33885-102">Задание или изменение параметров сортировки столбца</span><span class="sxs-lookup"><span data-stu-id="33885-102">Set or Change the Column Collation</span></span>
  <span data-ttu-id="33885-103">Для типов данных `char`, `varchar`, `text`, `nchar`, `nvarchar` и `ntext` параметры сортировки базы данных можно переопределить, указав другие параметры сортировки для определенного столбца таблицы одним из следующих способов.</span><span class="sxs-lookup"><span data-stu-id="33885-103">You can override the database collation for `char`, `varchar`, `text`, `nchar`, `nvarchar`, and `ntext` data by specifying a different collation for a specific column of a table and using one of the following:</span></span>  
  
-   <span data-ttu-id="33885-104">Предложением COLLATE в инструкциях [CREATE TABLE](/sql/t-sql/statements/create-table-transact-sql) и [ALTER TABLE](/sql/t-sql/statements/alter-table-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="33885-104">The COLLATE clause of [CREATE TABLE](/sql/t-sql/statements/create-table-transact-sql) and [ALTER TABLE](/sql/t-sql/statements/alter-table-transact-sql).</span></span> <span data-ttu-id="33885-105">Пример:</span><span class="sxs-lookup"><span data-stu-id="33885-105">For example:</span></span>  
  
    ```  
    CREATE TABLE dbo.MyTable  
      (PrimaryKey   int PRIMARY KEY,  
       CharCol      varchar(10) COLLATE French_CI_AS NOT NULL  
      );  
    GO  
    ALTER TABLE dbo.MyTable ALTER COLUMN CharCol  
                varchar(10)COLLATE Latin1_General_CI_AS NOT NULL;  
    GO  
    ```  
  
-   [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]<span data-ttu-id="33885-106">.</span><span class="sxs-lookup"><span data-stu-id="33885-106">.</span></span> <span data-ttu-id="33885-107">Дополнительные сведения см. в разделе [Collation and Unicode Support](collation-and-unicode-support.md).</span><span class="sxs-lookup"><span data-stu-id="33885-107">For more information, [Collation and Unicode Support](collation-and-unicode-support.md).</span></span>  
  
-   <span data-ttu-id="33885-108">Использование `Column.Collation` свойства в [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] управляющих объектах (SMO).</span><span class="sxs-lookup"><span data-stu-id="33885-108">Using the `Column.Collation` property in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Management Objects (SMO).</span></span>  
  
 <span data-ttu-id="33885-109">Невозможно изменить параметры сортировки столбца, на который ссылаются:</span><span class="sxs-lookup"><span data-stu-id="33885-109">You cannot change the collation of a column that is currently referenced by any one of the following:</span></span>  
  
-   <span data-ttu-id="33885-110">вычисляемый столбец;</span><span class="sxs-lookup"><span data-stu-id="33885-110">A computed column</span></span>  
  
-   <span data-ttu-id="33885-111">индекс;</span><span class="sxs-lookup"><span data-stu-id="33885-111">An index</span></span>  
  
-   <span data-ttu-id="33885-112">статистика распределения, созданная автоматически либо с помощью инструкции CREATE STATISTICS;</span><span class="sxs-lookup"><span data-stu-id="33885-112">Distribution statistics, either generated automatically or by the CREATE STATISTICS statement</span></span>  
  
-   <span data-ttu-id="33885-113">ограничение CHECK;</span><span class="sxs-lookup"><span data-stu-id="33885-113">A CHECK constraint</span></span>  
  
-   <span data-ttu-id="33885-114">ограничение FOREIGN KEY.</span><span class="sxs-lookup"><span data-stu-id="33885-114">A FOREIGN KEY constraint</span></span>  
  
 <span data-ttu-id="33885-115">При работе с базой данных **tempdb**предложение [COLLATE](/sql/t-sql/statements/collations) содержит параметр *database_default* , указывающий, что столбец, находящийся во временной таблице, использует параметры сортировки по умолчанию для текущей базы данных пользователя для соединения, а не параметра сортировки базы данных **tempdb**.</span><span class="sxs-lookup"><span data-stu-id="33885-115">When you work with **tempdb**, the [COLLATE](/sql/t-sql/statements/collations) clause includes a *database_default* option to specify that a column in a temporary table uses the collation default of the current user database for the connection instead of the collation of **tempdb**.</span></span>  
  
## <a name="collations-and-text-columns"></a><span data-ttu-id="33885-116">Параметры сортировки и столбцы типа text</span><span class="sxs-lookup"><span data-stu-id="33885-116">Collations and text Columns</span></span>  
 <span data-ttu-id="33885-117">В столбце типа `text` можно добавлять или обновлять значения, имеющие параметры сортировки, отличные от кодовой страницы параметров сортировки по умолчанию для базы данных.</span><span class="sxs-lookup"><span data-stu-id="33885-117">You can insert or update values in a `text` column whose collation is different from the code page of the default collation of the database.</span></span> [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="33885-118">неявно преобразует значения в параметры сортировки столбца.</span><span class="sxs-lookup"><span data-stu-id="33885-118">implicitly converts the values to the collation of the column.</span></span>  
  
## <a name="collations-and-tempdb"></a><span data-ttu-id="33885-119">Параметры сортировки и база данных tempdb</span><span class="sxs-lookup"><span data-stu-id="33885-119">Collations and tempdb</span></span>  
 <span data-ttu-id="33885-120">База данных **tempdb** создается каждый раз при запуске [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] и имеет те же параметры сортировки по умолчанию, что и база данных **model** .</span><span class="sxs-lookup"><span data-stu-id="33885-120">The **tempdb** database is built every time [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] is started and has the same default collation as the **model** database.</span></span> <span data-ttu-id="33885-121">Обычно они совпадают с параметрами сортировки экземпляра.</span><span class="sxs-lookup"><span data-stu-id="33885-121">This is typically the same as the default collation of the instance.</span></span> <span data-ttu-id="33885-122">Если при создании пользовательской базы данных указываются параметры сортировки, отличные от параметров сортировки базы данных **model**, то параметры сортировки пользовательской базы данных будут отличаться от базы данных **tempdb**.</span><span class="sxs-lookup"><span data-stu-id="33885-122">If you create a user database and specify a different default collation than **model**, the user database has a different default collation than **tempdb**.</span></span> <span data-ttu-id="33885-123">Все временные хранимые процедуры и временные таблицы создаются и сохраняются в базе данных **tempdb**.</span><span class="sxs-lookup"><span data-stu-id="33885-123">All temporary stored procedures or temporary tables are created and stored in **tempdb**.</span></span> <span data-ttu-id="33885-124">Это означает, что неявно столбцы временных таблиц и все константы, переменные и параметры хранимых процедур имеют параметры сортировки, отличные от сравниваемых объектов, создаваемых в постоянных таблицах и хранимых процедурах.</span><span class="sxs-lookup"><span data-stu-id="33885-124">This means that all implicit columns in temporary tables and all coercible-default constants, variables, and parameters in temporary stored procedures have collations that are different from comparable objects created in permanent tables and stored procedures.</span></span>  
  
 <span data-ttu-id="33885-125">Это может привести к проблемам из-за различия параметров сортировки у объектов в пользовательских и системных базах данных.</span><span class="sxs-lookup"><span data-stu-id="33885-125">This could lead to problems with a mismatch in collations between user-defined databases and system database objects.</span></span> <span data-ttu-id="33885-126">Например, экземпляр [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] использует параметры сортировки Latin1_General_CS_AS, выполняется следующая инструкция:</span><span class="sxs-lookup"><span data-stu-id="33885-126">For example, an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] uses the Latin1_General_CS_AS collation and you execute the following statements:</span></span>  
  
```  
CREATE DATABASE TestDB COLLATE Estonian_CS_AS;  
USE TestDB;  
CREATE TABLE TestPermTab (PrimaryKey int PRIMARY KEY, Col1 nchar );  
```  
  
 <span data-ttu-id="33885-127">В рассматриваемой системе база данных **tempdb** использует параметры сортировки Latin1_General_CS_AS с кодовой страницей 1252, а база данных `TestDB` и столбец `TestPermTab.Col1` — параметры сортировки `Estonian_CS_AS` с кодовой страницей 1257.</span><span class="sxs-lookup"><span data-stu-id="33885-127">In this system, the **tempdb** database uses the Latin1_General_CS_AS collation with code page 1252, and `TestDB` and `TestPermTab.Col1` use the `Estonian_CS_AS` collation with code page 1257.</span></span> <span data-ttu-id="33885-128">Пример:</span><span class="sxs-lookup"><span data-stu-id="33885-128">For example:</span></span>  
  
```  
USE TestDB;  
GO  
-- Create a temporary table with the same column declarations  
-- as TestPermTab  
CREATE TABLE #TestTempTab (PrimaryKey int PRIMARY KEY, Col1 nchar );  
INSERT INTO #TestTempTab  
         SELECT * FROM TestPermTab;  
GO  
```  
  
 <span data-ttu-id="33885-129">Согласно предыдущему примеру, база данных **tempdb** использует параметры сортировки Latin1_General_CS_AS, а база данных `TestDB` и столбец `TestTab.Col1` параметры сортировки `Estonian_CS_AS` .</span><span class="sxs-lookup"><span data-stu-id="33885-129">With the previous example, the **tempdb** database uses the Latin1_General_CS_AS collation, and `TestDB` and `TestTab.Col1` use the `Estonian_CS_AS` collation.</span></span> <span data-ttu-id="33885-130">Пример:</span><span class="sxs-lookup"><span data-stu-id="33885-130">For example:</span></span>  
  
```  
SELECT * FROM TestPermTab AS a INNER JOIN #TestTempTab on a.Col1 = #TestTempTab.Col1;  
```  
  
 <span data-ttu-id="33885-131">Поскольку база данных **tempdb** использует параметры сортировки сервера по умолчанию, а `TestPermTab.Col1` — другие параметры сортировки, SQL Server возвратит следующую ошибку: "Не удалось разрешить конфликт параметров сортировки между "Latin1_General_CI_AS_KS_WS" и "Estonian_CS_AS" в операции равенства".</span><span class="sxs-lookup"><span data-stu-id="33885-131">Because **tempdb** uses the default server collation and `TestPermTab.Col1` uses a different collation, SQL Server returns this error: "Cannot resolve collation conflict between 'Latin1_General_CI_AS_KS_WS' and 'Estonian_CS_AS' in equal to operation."</span></span>  
  
 <span data-ttu-id="33885-132">Избавиться от этой ошибки можно одним из следующих способов:</span><span class="sxs-lookup"><span data-stu-id="33885-132">To prevent the error, you can use one of the following alternatives:</span></span>  
  
-   <span data-ttu-id="33885-133">укажите, что столбец временной таблицы использует параметры сортировки по умолчанию пользовательской базы данных, а не базы данных **tempdb**.</span><span class="sxs-lookup"><span data-stu-id="33885-133">Specify that the temporary table column use the default collation of the user database, not **tempdb**.</span></span> <span data-ttu-id="33885-134">Это позволит таблице работать с аналогичными таблицами в разных базах данных, если это необходимо;</span><span class="sxs-lookup"><span data-stu-id="33885-134">This enables the temporary table to work with similarly formatted tables in multiple databases, if that is required of your system.</span></span>  
  
    ```  
    CREATE TABLE #TestTempTab  
       (PrimaryKey int PRIMARY KEY,  
        Col1 nchar COLLATE database_default  
       );  
    ```  
  
-   <span data-ttu-id="33885-135">укажите правильные параметры сортировки в столбце `#TestTempTab` :</span><span class="sxs-lookup"><span data-stu-id="33885-135">Specify the correct collation for the `#TestTempTab` column:</span></span>  
  
    ```  
    CREATE TABLE #TestTempTab  
       (PrimaryKey int PRIMARY KEY,  
        Col1 nchar COLLATE Estonian_CS_AS  
       );  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="33885-136">См. также:</span><span class="sxs-lookup"><span data-stu-id="33885-136">See Also</span></span>  
 <span data-ttu-id="33885-137">[Установка или изменение параметров сортировки сервера](set-or-change-the-server-collation.md) </span><span class="sxs-lookup"><span data-stu-id="33885-137">[Set or Change the Server Collation](set-or-change-the-server-collation.md) </span></span>  
 <span data-ttu-id="33885-138">[Установка и изменение параметров сортировки базы данных](set-or-change-the-database-collation.md) </span><span class="sxs-lookup"><span data-stu-id="33885-138">[Set or Change the Database Collation](set-or-change-the-database-collation.md) </span></span>  
 [<span data-ttu-id="33885-139">Поддержка параметров сортировки и Юникода</span><span class="sxs-lookup"><span data-stu-id="33885-139">Collation and Unicode Support</span></span>](collation-and-unicode-support.md)  
  
  
