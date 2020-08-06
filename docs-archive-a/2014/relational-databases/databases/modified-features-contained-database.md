---
title: Измененные функции (автономная база данных) | Документация Майкрософт
ms.custom: ''
ms.date: 07/17/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
helpviewer_keywords:
- contained database, modifications to DBs
ms.assetid: a2942509-39a2-4903-b504-ae80a300a9de
author: stevestein
ms.author: sstein
ms.openlocfilehash: bc52821deeb879022881f838c61823b23c0c10c8
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87751056"
---
# <a name="modified-features-contained-database"></a><span data-ttu-id="859bd-102">Измененные функции (автономная база данных)</span><span class="sxs-lookup"><span data-stu-id="859bd-102">Modified Features (Contained Database)</span></span>
  <span data-ttu-id="859bd-103">Для поддержки частично автономных баз данных в следующие функции были внесены изменения.</span><span class="sxs-lookup"><span data-stu-id="859bd-103">The following features have been modified to be supported by a partially contained database.</span></span> <span data-ttu-id="859bd-104">Обычно функции изменяются для того, чтобы они не пересекали границу базы данных.</span><span class="sxs-lookup"><span data-stu-id="859bd-104">Features are usually modified so they do not cross the database boundary.</span></span>  
  
 <span data-ttu-id="859bd-105">Дополнительные сведения см. в разделе [Contained Databases](contained-databases.md).</span><span class="sxs-lookup"><span data-stu-id="859bd-105">For more information, see [Contained Databases](contained-databases.md).</span></span>  
  
## <a name="alter-database"></a><span data-ttu-id="859bd-106">ALTER DATABASE</span><span class="sxs-lookup"><span data-stu-id="859bd-106">ALTER DATABASE</span></span>  
  
### <a name="application-level"></a><span data-ttu-id="859bd-107">Уровень приложения</span><span class="sxs-lookup"><span data-stu-id="859bd-107">Application Level</span></span>  
 <span data-ttu-id="859bd-108">При использовании инструкции ALTER DATABASE в автономной базе данных ее синтаксис отличается от синтаксиса при использовании в неавтономной базе данных.</span><span class="sxs-lookup"><span data-stu-id="859bd-108">When using the ALTER DATABASE statement from inside of a contained database, the syntax differs from that used for a non-contained database.</span></span> <span data-ttu-id="859bd-109">Различия включают ограничения на элементы инструкции, действие которых выходит за рамки базы данных на уровень экземпляра.</span><span class="sxs-lookup"><span data-stu-id="859bd-109">This difference includes restrictions of elements of the statement that extend beyond the database to the instance.</span></span> <span data-ttu-id="859bd-110">Дополнительные сведения см. в разделе [ALTER DATABASE (Transact-SQL)](/sql/t-sql/statements/alter-database-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="859bd-110">For more information, see [ALTER DATABASE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql).</span></span>  
  
### <a name="instance-level"></a><span data-ttu-id="859bd-111">Уровень экземпляра</span><span class="sxs-lookup"><span data-stu-id="859bd-111">Instance Level</span></span>  
 <span data-ttu-id="859bd-112">При использовании инструкции ALTER DATABASE применительно к автономной базе данных из-за пределов этой базы данных ее синтаксис отличается от синтаксиса при использовании в неавтономной базе данных.</span><span class="sxs-lookup"><span data-stu-id="859bd-112">The syntax for the ALTER DATABASE when used outside of a contained database differs from that used for non-contained databases.</span></span> <span data-ttu-id="859bd-113">Эти изменения позволяют не допустить пересечения границы базы данных.</span><span class="sxs-lookup"><span data-stu-id="859bd-113">These changes prevent crossing the database boundary.</span></span> <span data-ttu-id="859bd-114">Дополнительные сведения см. в разделе [ALTER DATABASE (Transact-SQL)](/sql/t-sql/statements/alter-database-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="859bd-114">For more information, see [ALTER DATABASE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql).</span></span>  
  
## <a name="create-database"></a><span data-ttu-id="859bd-115">CREATE DATABASE</span><span class="sxs-lookup"><span data-stu-id="859bd-115">CREATE DATABASE</span></span>  
 <span data-ttu-id="859bd-116">При использовании инструкции CREATE DATABASE для автономной базы данных ее синтаксис отличается от синтаксиса при использовании для неавтономной базы данных.</span><span class="sxs-lookup"><span data-stu-id="859bd-116">The CREATE DATABASE syntax for a contained database differs from that for a non-contained database.</span></span> <span data-ttu-id="859bd-117">Дополнительные сведения о новых требованиях и допущениях синтаксиса см. в статье [CREATE DATABASE (SQL Server Transact-SQL)](/sql/t-sql/statements/create-database-sql-server-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="859bd-117">See [CREATE DATABASE &#40;SQL Server Transact-SQL&#41;](/sql/t-sql/statements/create-database-sql-server-transact-sql)for information about new syntax requirements and allowances.</span></span>  
  
## <a name="temporary-tables"></a><span data-ttu-id="859bd-118">Временные таблицы</span><span class="sxs-lookup"><span data-stu-id="859bd-118">Temporary Tables</span></span>  
 <span data-ttu-id="859bd-119">Локальные временные таблицы в автономных базах данных допускаются, но их поведение отличается от поведения таких таблиц в неавтономных базах данных.</span><span class="sxs-lookup"><span data-stu-id="859bd-119">Local temporary tables are permitted within a contained database, but their behavior differs from those in non-contained databases.</span></span> <span data-ttu-id="859bd-120">В неавтономных базах данных данные во временных таблицах сортируются в соответствии с параметрами сортировки **tempdb**.</span><span class="sxs-lookup"><span data-stu-id="859bd-120">In non-contained databases, temporary table data is collated in the collation of **tempdb**.</span></span> <span data-ttu-id="859bd-121">В автономной базе данных данные во временных таблицах сортируются в соответствии с параметрами сортировки автономной базы данных.</span><span class="sxs-lookup"><span data-stu-id="859bd-121">In a contained database temporary table data is collated in the collation of the contained database.</span></span>  
  
 <span data-ttu-id="859bd-122">Все метаданные, связанные со временными таблицами (например, имена таблиц и столбцов, индексов и т. п.), будут иметь параметры сортировки каталога.</span><span class="sxs-lookup"><span data-stu-id="859bd-122">All metadata associated with temporary tables (for example, table and column names, indexes, and so on) will be in the catalog collation.</span></span>  
  
 <span data-ttu-id="859bd-123">Во временных таблицах не могут использоваться именованные ограничения.</span><span class="sxs-lookup"><span data-stu-id="859bd-123">Named constraints may not be used in temporary tables.</span></span>  
  
 <span data-ttu-id="859bd-124">Временные таблицы не могут ссылаться на определяемые пользователем типы, коллекции схем XML или определяемые пользователем функции.</span><span class="sxs-lookup"><span data-stu-id="859bd-124">Temporary tables may not refer to user-defined types, XML schema collections, or user-defined functions.</span></span>  
  
## <a name="collation"></a><span data-ttu-id="859bd-125">Параметры сортировки</span><span class="sxs-lookup"><span data-stu-id="859bd-125">Collation</span></span>  
 <span data-ttu-id="859bd-126">В модели неавтономной базы данных имеется три раздельных типа параметров сортировки: параметры сортировки базы данных, параметры сортировки экземпляра и параметры сортировки tempdb.</span><span class="sxs-lookup"><span data-stu-id="859bd-126">In the non-contained database model, there are three separate types of collation: Database collation, Instance collation, and tempdb collation.</span></span> <span data-ttu-id="859bd-127">В автономных базах данных используются только два набора параметров сортировки: параметры сортировки базы данных и параметры сортировки новых каталогов.</span><span class="sxs-lookup"><span data-stu-id="859bd-127">Contained databases use only two collations, database collation and the new catalog collation.</span></span> <span data-ttu-id="859bd-128">Дополнительные сведения о параметрах сортировки в автономных базах данных см. в разделе [Contained Database Collations](contained-database-collations.md) .</span><span class="sxs-lookup"><span data-stu-id="859bd-128">See [Contained Database Collations](contained-database-collations.md) for more details on contained database collation.</span></span>  
  
## <a name="user-options"></a><span data-ttu-id="859bd-129">Пользовательские параметры</span><span class="sxs-lookup"><span data-stu-id="859bd-129">User Options</span></span>  
 <span data-ttu-id="859bd-130">При включении поддержки автономных баз данных необходимо установить [параметр «пользовательские параметры»](../../database-engine/configure-windows/configure-the-user-options-server-configuration-option.md) в значение 0 для экземпляра [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="859bd-130">When enabling contained databases, the [user options Option](../../database-engine/configure-windows/configure-the-user-options-server-configuration-option.md) must be set to 0 for the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="859bd-131">См. также:</span><span class="sxs-lookup"><span data-stu-id="859bd-131">See Also</span></span>  
 <span data-ttu-id="859bd-132">[Параметры сортировки автономной базы данных](contained-database-collations.md) </span><span class="sxs-lookup"><span data-stu-id="859bd-132">[Contained Database Collations](contained-database-collations.md) </span></span>  
 [<span data-ttu-id="859bd-133">Автономные базы данных</span><span class="sxs-lookup"><span data-stu-id="859bd-133">Contained Databases</span></span>](contained-databases.md)  
  
  
