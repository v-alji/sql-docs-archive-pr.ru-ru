---
title: Параметры сортировки автономной базы данных | Документация Майкрософт
ms.custom: ''
ms.date: 07/17/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
helpviewer_keywords:
- contained database, collations
ms.assetid: 4b44f6b9-2359-452f-8bb1-5520f2528483
author: stevestein
ms.author: sstein
ms.openlocfilehash: 2648dbedea7708c4f39c922c56bba96cf38b0c0e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87734138"
---
# <a name="contained-database-collations"></a><span data-ttu-id="50a89-102">Параметры сортировки автономной базы данных</span><span class="sxs-lookup"><span data-stu-id="50a89-102">Contained Database Collations</span></span>
  <span data-ttu-id="50a89-103">На порядок сортировки и семантику сравнения текстовых данных влияют различные свойства, в том числе учет регистра, учет диакритических знаков и используемый базовый язык.</span><span class="sxs-lookup"><span data-stu-id="50a89-103">Various properties affect the sort order and equality semantics of textual data, including case sensitivity, accent sensitivity, and the base language being used.</span></span> <span data-ttu-id="50a89-104">Эти характеристики выражаются в [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] посредством выбора параметров сортировки для данных.</span><span class="sxs-lookup"><span data-stu-id="50a89-104">These qualities are expressed to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] through the choice of collation for the data.</span></span> <span data-ttu-id="50a89-105">Подробное обсуждение параметров сортировки см. в разделе [Поддержка параметров сортировки и Юникода](../collations/collation-and-unicode-support.md).</span><span class="sxs-lookup"><span data-stu-id="50a89-105">For a more in-depth discussion of collations themselves, see [Collation and Unicode Support](../collations/collation-and-unicode-support.md).</span></span>  
  
 <span data-ttu-id="50a89-106">Параметры сортировки применяются не только к данным, хранящимся в пользовательских таблицах, но и ко всему тексту, обрабатываемому [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], включая метаданные, временные объекты, имена переменных и т. д. Обработка таких объектов в автономных и неавтономных базах данных различается.</span><span class="sxs-lookup"><span data-stu-id="50a89-106">Collations apply not only to data stored in user tables, but to all text handled by [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], including metadata, temporary objects, variable names, etc. The handling of these differs in contained and non-contained databases.</span></span> <span data-ttu-id="50a89-107">Это изменение коснется небольшого числа пользователей и обеспечит независимость и единообразие экземпляров.</span><span class="sxs-lookup"><span data-stu-id="50a89-107">This change will not affect many users, but helps provide instance independence and uniformity.</span></span> <span data-ttu-id="50a89-108">При этом возможны некоторые затруднения, а также проблемы в сеансах, которые обращаются и к автономным и к неавтономным базам данных.</span><span class="sxs-lookup"><span data-stu-id="50a89-108">But this may also cause some confusion, as well as problems for sessions that access both contained and non-contained databases.</span></span>  
  
 <span data-ttu-id="50a89-109">В этом разделе поясняется суть изменения и рассматриваются области, в которых оно может вызвать проблемы.</span><span class="sxs-lookup"><span data-stu-id="50a89-109">This topic clarifies the content of the change, and examines areas where the change may cause problems.</span></span>  
  
## <a name="non-contained-databases"></a><span data-ttu-id="50a89-110">Неавтономные базы данных</span><span class="sxs-lookup"><span data-stu-id="50a89-110">Non-Contained Databases</span></span>  
 <span data-ttu-id="50a89-111">Все базы данных имеют параметры сортировки по умолчанию (их можно задать во время создания или изменения базы данных).</span><span class="sxs-lookup"><span data-stu-id="50a89-111">All databases have a default collation (which can be set when creating or altering a database.</span></span> <span data-ttu-id="50a89-112">Эти параметры сортировки используются для всех метаданных в базе данных, а также по умолчанию для всех строковых столбцов в базе данных.</span><span class="sxs-lookup"><span data-stu-id="50a89-112">This collation is used for all metadata in the database, as well as the default for all string columns within the database.</span></span> <span data-ttu-id="50a89-113">Пользователи могут выбрать другие параметры сортировки для любого столбца с помощью предложения `COLLATE`.</span><span class="sxs-lookup"><span data-stu-id="50a89-113">Users can choose a different collation for any particular column by using the `COLLATE` clause.</span></span>  
  
### <a name="example-1"></a><span data-ttu-id="50a89-114">Пример 1</span><span class="sxs-lookup"><span data-stu-id="50a89-114">Example 1</span></span>  
 <span data-ttu-id="50a89-115">Например, для работы в Пекине можно использовать параметры сортировки китайского языка:</span><span class="sxs-lookup"><span data-stu-id="50a89-115">For example, if we were working in Beijing, we might use a Chinese collation:</span></span>  
  
```sql  
ALTER DATABASE MyDB COLLATE Chinese_Simplified_Pinyin_100_CI_AS;  
```  
  
 <span data-ttu-id="50a89-116">Теперь для создаваемого столбца по умолчанию будут применяться параметры сортировки китайского языка, но в случае необходимости можно выбрать другие параметры.</span><span class="sxs-lookup"><span data-stu-id="50a89-116">Now if we create a column, its default collation will be this Chinese collation, but we can choose another one if we want:</span></span>  
  
```sql  
CREATE TABLE MyTable  
      (mycolumn1 nvarchar,  
      mycolumn2 nvarchar COLLATE Frisian_100_CS_AS);  
GO  
SELECT name, collation_name  
FROM sys.columns  
WHERE name LIKE 'mycolumn%' ;  
GO  
```  
  
 [!INCLUDE[ssResult](../../includes/ssresult-md.md)]  
  
```sql  
name            collation_name  
--------------- ----------------------------------  
mycolumn1       Chinese_Simplified_Pinyin_100_CI_AS  
mycolumn2       Frisian_100_CS_AS  
```  
  
 <span data-ttu-id="50a89-117">Это выглядит довольно простым, однако возникают некоторые проблемы.</span><span class="sxs-lookup"><span data-stu-id="50a89-117">This appears relatively simple, but several problems arise.</span></span> <span data-ttu-id="50a89-118">Поскольку параметры сортировки для столбца зависят от базы данных, в которой создается таблица, возникают проблемы с использованием временных таблиц, которые хранятся в `tempdb` .</span><span class="sxs-lookup"><span data-stu-id="50a89-118">Because the collation for a column is dependent on the database in which the table is created, problems arise with the use of temporary tables which are stored in `tempdb`.</span></span> <span data-ttu-id="50a89-119">Параметры сортировки `tempdb` обычно соответствуют параметрам сортировки для экземпляра, который не должен соответствовать параметрам сортировки базы данных.</span><span class="sxs-lookup"><span data-stu-id="50a89-119">The collation of `tempdb` usually matches the collation for the instance, which does not have to match the database collation.</span></span>  
  
### <a name="example-2"></a><span data-ttu-id="50a89-120">Пример 2</span><span class="sxs-lookup"><span data-stu-id="50a89-120">Example 2</span></span>  
 <span data-ttu-id="50a89-121">Например, пусть база данных с китайскими параметрами сортировки (упомянутая выше) используется в экземпляре с параметрами сортировки **Latin1_General** :</span><span class="sxs-lookup"><span data-stu-id="50a89-121">For example, consider the (Chinese) database above when used on an instance with a **Latin1_General** collation:</span></span>  
  
```sql  
CREATE TABLE T1 (T1_txt nvarchar(max)) ;  
GO  
CREATE TABLE #T2 (T2_txt nvarchar(max)) ;  
GO  
```  
  
 <span data-ttu-id="50a89-122">На первый взгляд кажется, что две таблицы имеют одинаковую схему, однако из-за различия в параметрах сортировки баз данных значения оказываются несовместимыми.</span><span class="sxs-lookup"><span data-stu-id="50a89-122">At first glance, these two tables look like they have the same schema, but since the collations of the databases differ, the values are actually incompatible:</span></span>  
  
```  
SELECT T1_txt, T2_txt  
FROM T1   
JOIN #T2   
    ON T1.T1_txt = #T2.T2_txt  
```  
  
 [!INCLUDE[ssResult](../../includes/ssresult-md.md)]  
  
 <span data-ttu-id="50a89-123">Сообщение 468, уровень 16, состояние 9, строка 2</span><span class="sxs-lookup"><span data-stu-id="50a89-123">Msg 468, Level 16, State 9, Line 2</span></span>  
  
 <span data-ttu-id="50a89-124">Не удается разрешить конфликт параметров сортировки Latin1_General_100_CI_AS_KS_WS_SC и Chinese_Simplified_Pinyin_100_CI_AS в операции равенства.</span><span class="sxs-lookup"><span data-stu-id="50a89-124">Cannot resolve the collation conflict between "Latin1_General_100_CI_AS_KS_WS_SC" and Chinese_Simplified_Pinyin_100_CI_AS" in the equal to operation.</span></span>  
  
 <span data-ttu-id="50a89-125">Чтобы исправить эту проблему, можно явно задать параметры сортировки временной таблицы.</span><span class="sxs-lookup"><span data-stu-id="50a89-125">We can fix this by explicitly collating the temporary table.</span></span> <span data-ttu-id="50a89-126">В [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] эта задача несколько упрощается за счет поддержки ключевого слова `DATABASE_DEFAULT` для предложения `COLLATE`.</span><span class="sxs-lookup"><span data-stu-id="50a89-126">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] makes this somewhat easier by providing the `DATABASE_DEFAULT` keyword for the `COLLATE` clause.</span></span>  
  
```sql  
CREATE TABLE T1 (T1_txt nvarchar(max)) ;  
GO  
CREATE TABLE #T2 (T2_txt nvarchar(max) COLLATE DATABASE_DEFAULT);  
GO  
SELECT T1_txt, T2_txt  
FROM T1   
JOIN #T2   
    ON T1.T1_txt = #T2.T2_txt ;  
```  
  
 <span data-ttu-id="50a89-127">Теперь операция работает без ошибки.</span><span class="sxs-lookup"><span data-stu-id="50a89-127">This now runs without error.</span></span>  
  
 <span data-ttu-id="50a89-128">Различия параметров сортировки также проявляются в обработке переменных.</span><span class="sxs-lookup"><span data-stu-id="50a89-128">We can also see collation-dependent behavior with variables.</span></span> <span data-ttu-id="50a89-129">Рассмотрим следующую функцию:</span><span class="sxs-lookup"><span data-stu-id="50a89-129">Consider the following function:</span></span>  
  
```  
CREATE FUNCTION f(@x INT) RETURNS INT  
AS BEGIN   
      DECLARE @I INT = 1  
      DECLARE @?? INT = 2  
      RETURN @x * @i  
END;  
```  
  
 <span data-ttu-id="50a89-130">Это довольно необычная функция.</span><span class="sxs-lookup"><span data-stu-id="50a89-130">This is a rather peculiar function.</span></span> <span data-ttu-id="50a89-131">В параметрах сортировки с учетом регистра элемент @i в предложении RETURN не может быть привязан либо к, либо к @I @??.</span><span class="sxs-lookup"><span data-stu-id="50a89-131">In a case-sensitive collation, the @i in the return clause cannot bind to either @I or @??.</span></span> <span data-ttu-id="50a89-132">Если сортировка выполняется как Latin1_General без учета регистра, конструкция @i привязывается к @I и функция возвращает значение 1.</span><span class="sxs-lookup"><span data-stu-id="50a89-132">In a case-insensitive Latin1_General collation, @i binds to @I, and the function returns 1.</span></span> <span data-ttu-id="50a89-133">Но в параметрах сортировки, не учитывающих регистр, выполняется @i Привязка к @??, и функция возвращает значение 2.</span><span class="sxs-lookup"><span data-stu-id="50a89-133">But in a case-insensitive Turkish collation, @i binds to @??, and the function returns 2.</span></span> <span data-ttu-id="50a89-134">Это может негативно отразиться на базе данных, которая перемещается между экземплярами с различными параметрами сортировки.</span><span class="sxs-lookup"><span data-stu-id="50a89-134">This can wreak havoc on a database that moves between instances with different collations.</span></span>  
  
## <a name="contained-databases"></a><span data-ttu-id="50a89-135">Автономные базы данных</span><span class="sxs-lookup"><span data-stu-id="50a89-135">Contained Databases</span></span>  
 <span data-ttu-id="50a89-136">Поскольку задачей проектирования автономных баз данных является обеспечение их независимости, необходимо исключить зависимость от параметров сортировки экземпляра и базы данных `tempdb`.</span><span class="sxs-lookup"><span data-stu-id="50a89-136">Since a design objective of contained databases is to make them self-contained, the dependence on the instance and `tempdb` collations must be severed.</span></span> <span data-ttu-id="50a89-137">Для этого в автономных базах данных реализовано основное понятие параметров сортировки каталога.</span><span class="sxs-lookup"><span data-stu-id="50a89-137">To do this, contained databases introduce the concept of the catalog collation.</span></span> <span data-ttu-id="50a89-138">Параметры сортировки каталога используются для метаданных системы и временных объектов.</span><span class="sxs-lookup"><span data-stu-id="50a89-138">The catalog collation is used for system metadata and transient objects.</span></span> <span data-ttu-id="50a89-139">Далее даны подробности.</span><span class="sxs-lookup"><span data-stu-id="50a89-139">Details are provided below.</span></span>  
  
 <span data-ttu-id="50a89-140">В автономной базе данных используются параметры сортировки каталога **Latin1_General_100_CI_AS_WS_KS_SC**.</span><span class="sxs-lookup"><span data-stu-id="50a89-140">In a contained database, the catalog collation **Latin1_General_100_CI_AS_WS_KS_SC**.</span></span> <span data-ttu-id="50a89-141">Эти параметры сортировки одинаковы для всех автономных баз данных во всех экземплярах [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , и их нельзя изменить.</span><span class="sxs-lookup"><span data-stu-id="50a89-141">This collation is the same for all contained databases on all instances of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] and cannot be changed.</span></span>  
  
 <span data-ttu-id="50a89-142">Параметры сортировки базы данных сохраняются, но используются только в качестве параметров сортировки по умолчанию для пользовательских данных.</span><span class="sxs-lookup"><span data-stu-id="50a89-142">The database collation is retained, but is only used as the default collation for user data.</span></span> <span data-ttu-id="50a89-143">По умолчанию параметры сортировки базы данных совпадают с параметрами сортировки базы данных model, но могут быть изменены пользователем с помощью `CREATE` команды или, `ALTER DATABASE` как и при работе с неавтономными базами данных.</span><span class="sxs-lookup"><span data-stu-id="50a89-143">By default, the database collation is equal to the model database collation, but can be changed by the user through a `CREATE` or `ALTER DATABASE` command as with non-contained databases.</span></span>  
  
 <span data-ttu-id="50a89-144">В предложении `CATALOG_DEFAULT` доступно новое ключевое слово `COLLATE`.</span><span class="sxs-lookup"><span data-stu-id="50a89-144">A new keyword, `CATALOG_DEFAULT`, is available in the `COLLATE` clause.</span></span> <span data-ttu-id="50a89-145">Оно служит ярлыком для текущих параметров сортировки метаданных и в автономных и в неавтономных базах данных.</span><span class="sxs-lookup"><span data-stu-id="50a89-145">This is used as a shortcut to the current collation of metadata in both contained and non-contained databases.</span></span> <span data-ttu-id="50a89-146">Это значит, что в неавтономной базе данных конструкция `CATALOG_DEFAULT` возвращает текущие параметры сортировки базы данных, поскольку в метаданных применяются параметры сортировки базы данных.</span><span class="sxs-lookup"><span data-stu-id="50a89-146">That is, in a non-contained database, `CATALOG_DEFAULT` will return the current database collation, since metadata is collated in the database collation.</span></span> <span data-ttu-id="50a89-147">В автономной базе данных эти два значения могут различаться, поскольку пользователь может изменить параметры сортировки базы данных так, чтобы они отличались от параметров сортировки каталога.</span><span class="sxs-lookup"><span data-stu-id="50a89-147">In a contained database, these two values may be different, since the user can change the database collation so that it does not match the catalog collation.</span></span>  
  
 <span data-ttu-id="50a89-148">В данной таблице представлен порядок обработки различных объектов в автономных и неавтономных базах данных.</span><span class="sxs-lookup"><span data-stu-id="50a89-148">The behavior of various objects in both non-contained and contained databases is summarized in this table:</span></span>  
  
||||  
|-|-|-|  
|<span data-ttu-id="50a89-149">**Item**</span><span class="sxs-lookup"><span data-stu-id="50a89-149">**Item**</span></span>|<span data-ttu-id="50a89-150">**Неавтономная база данных**</span><span class="sxs-lookup"><span data-stu-id="50a89-150">**Non-Contained Database**</span></span>|<span data-ttu-id="50a89-151">**Автономная база данных**</span><span class="sxs-lookup"><span data-stu-id="50a89-151">**Contained Database**</span></span>|  
|<span data-ttu-id="50a89-152">Пользовательские данные (по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="50a89-152">User Data (default)</span></span>|<span data-ttu-id="50a89-153">DATABASE_DEFAULT</span><span class="sxs-lookup"><span data-stu-id="50a89-153">DATABASE_DEFAULT</span></span>|<span data-ttu-id="50a89-154">DATABASE_DEFAULT</span><span class="sxs-lookup"><span data-stu-id="50a89-154">DATABASE_DEFAULT</span></span>|  
|<span data-ttu-id="50a89-155">Временные данные (по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="50a89-155">Temp Data (default)</span></span>|<span data-ttu-id="50a89-156">Параметры сортировки TempDB</span><span class="sxs-lookup"><span data-stu-id="50a89-156">TempDB Collation</span></span>|<span data-ttu-id="50a89-157">DATABASE_DEFAULT</span><span class="sxs-lookup"><span data-stu-id="50a89-157">DATABASE_DEFAULT</span></span>|  
|<span data-ttu-id="50a89-158">Метаданные</span><span class="sxs-lookup"><span data-stu-id="50a89-158">Metadata</span></span>|<span data-ttu-id="50a89-159">DATABASE_DEFAULT / CATALOG_DEFAULT</span><span class="sxs-lookup"><span data-stu-id="50a89-159">DATABASE_DEFAULT / CATALOG_DEFAULT</span></span>|<span data-ttu-id="50a89-160">CATALOG_DEFAULT</span><span class="sxs-lookup"><span data-stu-id="50a89-160">CATALOG_DEFAULT</span></span>|  
|<span data-ttu-id="50a89-161">Временные метаданные</span><span class="sxs-lookup"><span data-stu-id="50a89-161">Temporary Metadata</span></span>|<span data-ttu-id="50a89-162">Параметры сортировки TempDB</span><span class="sxs-lookup"><span data-stu-id="50a89-162">tempdb Collation</span></span>|<span data-ttu-id="50a89-163">CATALOG_DEFAULT</span><span class="sxs-lookup"><span data-stu-id="50a89-163">CATALOG_DEFAULT</span></span>|  
|<span data-ttu-id="50a89-164">Переменные</span><span class="sxs-lookup"><span data-stu-id="50a89-164">Variables</span></span>|<span data-ttu-id="50a89-165">Параметры сортировки экземпляра</span><span class="sxs-lookup"><span data-stu-id="50a89-165">Instance Collation</span></span>|<span data-ttu-id="50a89-166">CATALOG_DEFAULT</span><span class="sxs-lookup"><span data-stu-id="50a89-166">CATALOG_DEFAULT</span></span>|  
|<span data-ttu-id="50a89-167">Метки перехода</span><span class="sxs-lookup"><span data-stu-id="50a89-167">Goto Labels</span></span>|<span data-ttu-id="50a89-168">Параметры сортировки экземпляра</span><span class="sxs-lookup"><span data-stu-id="50a89-168">Instance Collation</span></span>|<span data-ttu-id="50a89-169">CATALOG_DEFAULT</span><span class="sxs-lookup"><span data-stu-id="50a89-169">CATALOG_DEFAULT</span></span>|  
|<span data-ttu-id="50a89-170">Имена курсоров</span><span class="sxs-lookup"><span data-stu-id="50a89-170">Cursor Names</span></span>|<span data-ttu-id="50a89-171">Параметры сортировки экземпляра</span><span class="sxs-lookup"><span data-stu-id="50a89-171">Instance Collation</span></span>|<span data-ttu-id="50a89-172">CATALOG_DEFAULT</span><span class="sxs-lookup"><span data-stu-id="50a89-172">CATALOG_DEFAULT</span></span>|  
  
 <span data-ttu-id="50a89-173">В ранее описанном примере с временной таблицей видно, что такой принцип работы параметров сортировки исключает необходимость явно задавать предложение `COLLATE` в большинстве случаев использования временной таблицы.</span><span class="sxs-lookup"><span data-stu-id="50a89-173">If we temp table example previously described, we can see that this collation behavior eliminates the need for an explicit `COLLATE` clause in most temp table uses.</span></span> <span data-ttu-id="50a89-174">В автономной базе данных этот код теперь работает без ошибок, даже в случае, когда параметры сортировки различаются для базы данных и для экземпляра.</span><span class="sxs-lookup"><span data-stu-id="50a89-174">In a contained database, this code now runs without error, even if the database and instance collations differ:</span></span>  
  
```sql  
CREATE TABLE T1 (T1_txt nvarchar(max)) ;  
GO  
CREATE TABLE #T2 (T2_txt nvarchar(max));  
GO  
SELECT T1_txt, T2_txt  
FROM T1   
JOIN #T2   
    ON T1.T1_txt = #T2.T2_txt ;  
```  
  
 <span data-ttu-id="50a89-175">Так происходит потому, что для `T1_txt` и `T2_txt` используются параметры сортировки автономной базы данных.</span><span class="sxs-lookup"><span data-stu-id="50a89-175">This works because both `T1_txt` and `T2_txt` are collated in the database collation of the contained database.</span></span>  
  
## <a name="crossing-between-contained-and-uncontained-contexts"></a><span data-ttu-id="50a89-176">Переход между автономными и неавтономными контекстами</span><span class="sxs-lookup"><span data-stu-id="50a89-176">Crossing Between Contained and Uncontained Contexts</span></span>  
 <span data-ttu-id="50a89-177">Пока сеанс в автономной базе данных остается автономным, он должен оставаться в пределах базы данных, с которой установлено соединение.</span><span class="sxs-lookup"><span data-stu-id="50a89-177">As long as a session in a contained database remains contained, it must remain within the database to which it connected.</span></span> <span data-ttu-id="50a89-178">В этом случае работа ведется очевидным образом.</span><span class="sxs-lookup"><span data-stu-id="50a89-178">In this case the behavior is very straightforward.</span></span> <span data-ttu-id="50a89-179">Однако если сеанс переходит между автономными и неавтономными контекстами, то его обработка усложняется, поскольку требуется организовать связь между двумя наборами правил.</span><span class="sxs-lookup"><span data-stu-id="50a89-179">But if a session crosses between contained and non-contained contexts, the behavior becomes more complex, since the two sets of rules must be bridged.</span></span> <span data-ttu-id="50a89-180">Такое может случаться в частично автономной базе данных, поскольку пользователь может передать команду `USE` в другую базу данных.</span><span class="sxs-lookup"><span data-stu-id="50a89-180">This can happen in a partially-contained database, since a user may `USE` to another database.</span></span> <span data-ttu-id="50a89-181">В этом случае различия в правилах параметров сортировки обрабатываются следующим образом.</span><span class="sxs-lookup"><span data-stu-id="50a89-181">In this case, the difference in collation rules is handled by the following principle.</span></span>  
  
-   <span data-ttu-id="50a89-182">Правило параметров сортировки для пакета определяется базой данных, в которой начинается пакет.</span><span class="sxs-lookup"><span data-stu-id="50a89-182">The collation behavior for a batch is determined by the database in which the batch begins.</span></span>  
  
 <span data-ttu-id="50a89-183">Заметьте, что это решение принимается до обработки команд, включая первоначальную команду `USE`.</span><span class="sxs-lookup"><span data-stu-id="50a89-183">Note that this decision is made before any commands are issued, including an initial `USE`.</span></span> <span data-ttu-id="50a89-184">Это значит, что если пакет начинается в автономной базе данных, но первая команда `USE` ссылается на неавтономную базу данных, то для пакета будут использоваться параметры сортировки для автономной базы данных.</span><span class="sxs-lookup"><span data-stu-id="50a89-184">That is, if a batch begins in a contained database, but the first command is a `USE` to a non-contained database, the contained collation behavior will still be used for the batch.</span></span> <span data-ttu-id="50a89-185">В отношении переменных это может приводить к различным результатам.</span><span class="sxs-lookup"><span data-stu-id="50a89-185">Given this, a reference to a variable, for example, may have multiple possible outcomes:</span></span>  
  
-   <span data-ttu-id="50a89-186">Ссылка может обнаружить ровно одно соответствие.</span><span class="sxs-lookup"><span data-stu-id="50a89-186">The reference may find exactly one match.</span></span> <span data-ttu-id="50a89-187">В этом случае ссылка будет работать без ошибок.</span><span class="sxs-lookup"><span data-stu-id="50a89-187">In this case, the reference will work without error.</span></span>  
  
-   <span data-ttu-id="50a89-188">Ссылка может не найти соответствия в текущих параметрах сортировки на прежней позиции.</span><span class="sxs-lookup"><span data-stu-id="50a89-188">The reference may not find a match in the current collation where there was one before.</span></span> <span data-ttu-id="50a89-189">В этом случае происходит ошибка, показывающая, что переменная не существует, хотя очевидно, что она была создана.</span><span class="sxs-lookup"><span data-stu-id="50a89-189">This will raise an error indicating that the variable does not exist, even though it was apparently created.</span></span>  
  
-   <span data-ttu-id="50a89-190">Ссылка может обнаружить несколько соответствий, которые прежде были различными.</span><span class="sxs-lookup"><span data-stu-id="50a89-190">The reference may find multiple matches that were originally distinct.</span></span> <span data-ttu-id="50a89-191">В этом случае также происходит ошибка.</span><span class="sxs-lookup"><span data-stu-id="50a89-191">This will also raise an error.</span></span>  
  
 <span data-ttu-id="50a89-192">Это показано в следующих примерах.</span><span class="sxs-lookup"><span data-stu-id="50a89-192">We'll illustrate this with a few examples.</span></span> <span data-ttu-id="50a89-193">Пусть имеется частично автономная база данных с именем `MyCDB` , для которой используются параметры сортировки каталога **Latin1_General_100_CI_AS_WS_KS_SC**.</span><span class="sxs-lookup"><span data-stu-id="50a89-193">For these we assume there is a partially-contained database named `MyCDB` with its database collation set to the default collation, **Latin1_General_100_CI_AS_WS_KS_SC**.</span></span> <span data-ttu-id="50a89-194">Пусть для экземпляра используются параметры сортировки `Latin1_General_100_CS_AS_WS_KS_SC`.</span><span class="sxs-lookup"><span data-stu-id="50a89-194">We assume that the instance collation is `Latin1_General_100_CS_AS_WS_KS_SC`.</span></span> <span data-ttu-id="50a89-195">Таким образом, два набора параметров сортировки различаются только учетом регистра.</span><span class="sxs-lookup"><span data-stu-id="50a89-195">The two collations differ only in case sensitivity.</span></span>  
  
### <a name="example-1"></a><span data-ttu-id="50a89-196">Пример 1</span><span class="sxs-lookup"><span data-stu-id="50a89-196">Example 1</span></span>  
 <span data-ttu-id="50a89-197">В следующем примере показан вариант, где ссылка обнаруживает ровно одно совпадение.</span><span class="sxs-lookup"><span data-stu-id="50a89-197">The following example illustrates the case where the reference finds exactly one match.</span></span>  
  
```  
USE MyCDB;  
GO  
  
CREATE TABLE #a(x int);  
INSERT INTO #a VALUES(1);  
GO  
  
USE master;  
GO  
  
SELECT * FROM #a;  
GO  
  
Results:  
  
```  
  
 [!INCLUDE[ssResult](../../includes/ssresult-md.md)]  
  
```  
x  
-----------  
1  
```  
  
 <span data-ttu-id="50a89-198">В данном случае конструкция #a привязывается к параметрам сортировки каталога (без учета регистра) и к параметрам сортировки экземпляра (с учетом регистра) и код работает.</span><span class="sxs-lookup"><span data-stu-id="50a89-198">In this case, the identified #a binds in both the case-insensitive catalog collation and the case-sensitive instance collation, and the code works.</span></span>  
  
### <a name="example-2"></a><span data-ttu-id="50a89-199">Пример 2</span><span class="sxs-lookup"><span data-stu-id="50a89-199">Example 2</span></span>  
 <span data-ttu-id="50a89-200">В следующим примере показан вариант, где ссылка не обнаруживает соответствие в текущих параметрах сортировки на прежней позиции.</span><span class="sxs-lookup"><span data-stu-id="50a89-200">The following example illustrates the case where the reference does not find a match in the current collation where there was one before.</span></span>  
  
```  
USE MyCDB;  
GO  
  
CREATE TABLE #a(x int);  
INSERT INTO #A VALUES(1);  
GO  
```  
  
 <span data-ttu-id="50a89-201">Здесь конструкция #A привязывается к #a в параметрах сортировки по умолчанию (без учета регистра) и операция вставки работает.</span><span class="sxs-lookup"><span data-stu-id="50a89-201">Here, the #A binds to #a in the case-insensitive default collation, and the insert works,</span></span>  
  
 [!INCLUDE[ssResult](../../includes/ssresult-md.md)]  
  
```  
(1 row(s) affected)  
```  
  
 <span data-ttu-id="50a89-202">Однако если работа скрипта продолжается...</span><span class="sxs-lookup"><span data-stu-id="50a89-202">But if we continue the script...</span></span>  
  
```  
USE master;  
GO  
  
SELECT * FROM #A;  
GO  
```  
  
 <span data-ttu-id="50a89-203">Возникает ошибка во время привязки к #A в параметрах сортировки экземпляра (с учетом регистра).</span><span class="sxs-lookup"><span data-stu-id="50a89-203">We get an error trying to bind to #A in the case-sensitive instance collation;</span></span>  
  
 [!INCLUDE[ssResult](../../includes/ssresult-md.md)]  
  
 <span data-ttu-id="50a89-204">Сообщение 208, уровень 16, состояние 0, строка 2</span><span class="sxs-lookup"><span data-stu-id="50a89-204">Msg 208, Level 16, State 0, Line 2</span></span>  
  
 <span data-ttu-id="50a89-205">Недопустимое имя объекта «#A».</span><span class="sxs-lookup"><span data-stu-id="50a89-205">Invalid object name '#A'.</span></span>  
  
### <a name="example-3"></a><span data-ttu-id="50a89-206">Пример 3</span><span class="sxs-lookup"><span data-stu-id="50a89-206">Example 3</span></span>  
 <span data-ttu-id="50a89-207">В следующем примере показан вариант, где ссылка обнаруживает несколько соответствий, которые прежде были различными.</span><span class="sxs-lookup"><span data-stu-id="50a89-207">The following example illustrates the case where the reference finds multiple matches that were originally distinct.</span></span> <span data-ttu-id="50a89-208">Сначала мы начнем с `tempdb` (в котором используются те же параметры сортировки с учетом регистра, что и у нашего экземпляра), и выполните следующие инструкции.</span><span class="sxs-lookup"><span data-stu-id="50a89-208">First, we start in `tempdb` (which has the same case-sensitive collation as our instance) and execute the following statements.</span></span>  
  
```  
USE tempdb;  
GO  
  
CREATE TABLE #a(x int);  
GO  
CREATE TABLE #A(x int);  
GO  
INSERT INTO #a VALUES(1);  
GO  
INSERT INTO #A VALUES(2);  
GO  
```  
  
 <span data-ttu-id="50a89-209">Он завершается успешно, поскольку в данных параметрах сортировки таблицы различны.</span><span class="sxs-lookup"><span data-stu-id="50a89-209">This succeeds, since the tables are distinct in this collation:</span></span>  
  
 [!INCLUDE[ssResult](../../includes/ssresult-md.md)]  
  
```  
(1 row(s) affected)  
(1 row(s) affected)  
```  
  
 <span data-ttu-id="50a89-210">Однако если перейти в автономную базу данных, то окажется, что привязка к этим таблицам уже невозможна.</span><span class="sxs-lookup"><span data-stu-id="50a89-210">If we move into our contained database, however, we find that we can no longer bind to these tables.</span></span>  
  
```  
USE MyCDB;  
GO  
SELECT * FROM #a;  
GO  
```  
  
 [!INCLUDE[ssResult](../../includes/ssresult-md.md)]  
  
 <span data-ttu-id="50a89-211">Сообщение 12800, уровень 16, состояние 1, строка 2</span><span class="sxs-lookup"><span data-stu-id="50a89-211">Msg 12800, Level 16, State 1, Line 2</span></span>  
  
 <span data-ttu-id="50a89-212">Не удается разрешить неоднозначную ссылку на временную таблицу с именем «#a».</span><span class="sxs-lookup"><span data-stu-id="50a89-212">The reference to temp table name '#a' is ambiguous and cannot be resolved.</span></span> <span data-ttu-id="50a89-213">Возможные варианты: «#a» и «#A».</span><span class="sxs-lookup"><span data-stu-id="50a89-213">Possible candidates are '#a' and '#A'.</span></span>  
  
## <a name="conclusion"></a><span data-ttu-id="50a89-214">Заключение</span><span class="sxs-lookup"><span data-stu-id="50a89-214">Conclusion</span></span>  
 <span data-ttu-id="50a89-215">Работа параметров сортировки в автономных базах данных несколько отличается от неавтономных баз данных.</span><span class="sxs-lookup"><span data-stu-id="50a89-215">The collation behavior of contained databases differs subtly from that in non-contained databases.</span></span> <span data-ttu-id="50a89-216">В целом эти изменения упрощают работу и обеспечивают независимость от экземпляра.</span><span class="sxs-lookup"><span data-stu-id="50a89-216">This behavior is generally beneficial, providing instance-independence and simplicity.</span></span> <span data-ttu-id="50a89-217">У некоторых пользователей могут возникать проблемы, особенно если сеанс обращается и к автономным и к неавтономным базам данных.</span><span class="sxs-lookup"><span data-stu-id="50a89-217">Some users may have issues, particularly when a session accesses both contained and non-contained databases.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="50a89-218">См. также:</span><span class="sxs-lookup"><span data-stu-id="50a89-218">See Also</span></span>  
 [<span data-ttu-id="50a89-219">Автономные базы данных</span><span class="sxs-lookup"><span data-stu-id="50a89-219">Contained Databases</span></span>](contained-databases.md)  
  
  
