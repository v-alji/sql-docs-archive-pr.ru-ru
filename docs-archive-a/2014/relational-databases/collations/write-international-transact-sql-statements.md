---
title: Написание инструкций Transact-SQL, адаптированных к международному использованию | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
helpviewer_keywords:
- writing international statements
- Transact-SQL international considerations
- international considerations [SQL Server], Transact-SQL
- Database Engine international considerations [SQL Server], Transact-SQL
- statements [SQL Server], international
- database international considerations [SQL Server], Transact-SQL
- dates [SQL Server], international considerations
ms.assetid: f0b10fee-27f7-45fe-aece-ccc3f63bdcdb
author: stevestein
ms.author: sstein
ms.openlocfilehash: 1888d1045e43e0a9839fd76a21c51500af63539a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87668906"
---
# <a name="write-international-transact-sql-statements"></a><span data-ttu-id="926dc-102">Написание инструкций Transact-SQL, адаптированных к международному использованию</span><span class="sxs-lookup"><span data-stu-id="926dc-102">Write International Transact-SQL Statements</span></span>
  <span data-ttu-id="926dc-103">В базах данных и использующих их приложениях, в которых применяются инструкции языка [!INCLUDE[tsql](../../includes/tsql-md.md)] , можно обеспечить большую степень языковой переносимости или поддержку нескольких языков при условии соблюдения следующих требований.</span><span class="sxs-lookup"><span data-stu-id="926dc-103">Databases and database applications that use [!INCLUDE[tsql](../../includes/tsql-md.md)] statements will become more portable from one language to another, or will support multiple languages, if the following guidelines are followed:</span></span>  
  
-   <span data-ttu-id="926dc-104">Все элементы с типами данных `char`, `varchar` и `text` замените элементами с типами данных `nchar`, `nvarchar` и `nvarchar(max)`.</span><span class="sxs-lookup"><span data-stu-id="926dc-104">Replace all uses of the `char`, `varchar`, and `text` data types with `nchar`, `nvarchar`, and `nvarchar(max)`.</span></span> <span data-ttu-id="926dc-105">Такая замена устраняет возможные проблемы с преобразованием кодовых страниц.</span><span class="sxs-lookup"><span data-stu-id="926dc-105">By doing this, you do not have to consider code page conversion issues.</span></span> <span data-ttu-id="926dc-106">Дополнительные сведения см. в статье [Collation and Unicode Support](collation-and-unicode-support.md).</span><span class="sxs-lookup"><span data-stu-id="926dc-106">For more information, see [Collation and Unicode Support](collation-and-unicode-support.md).</span></span>  
  
-   <span data-ttu-id="926dc-107">При выполнении сравнения и других операций со значениями месяцев и дней недели следует использовать числовые эквиваленты вместо строковых имен.</span><span class="sxs-lookup"><span data-stu-id="926dc-107">When you perform month and day-of-week comparisons and operations, use the numeric date parts instead of the name strings.</span></span> <span data-ttu-id="926dc-108">При различных языковых настройках возвращаются различные названия месяцев и дней недели.</span><span class="sxs-lookup"><span data-stu-id="926dc-108">Different language settings return different names for the months and weekdays.</span></span> <span data-ttu-id="926dc-109">Например, функция DATENAME(MONTH,GETDATE()) при выбранном английском (США) языке возвращает значение «May», при немецком — «Mai», а при французском — «mai».</span><span class="sxs-lookup"><span data-stu-id="926dc-109">For example, DATENAME(MONTH,GETDATE()) returns May when the language is set to U.S. English, returns Mai when the language is set to German, and returns mai when the language is set to French.</span></span> <span data-ttu-id="926dc-110">Вместо нее следует использовать функцию DATEPART(), в которой вместо названия месяца используется его номер.</span><span class="sxs-lookup"><span data-stu-id="926dc-110">Instead, use a function such as DATEPART that uses the number of the month instead of the name.</span></span> <span data-ttu-id="926dc-111">При выводе результирующих наборов пользователю лучше использовать названия из функции DATEPART(), так как они зачастую более информативны, чем числовое представление даты.</span><span class="sxs-lookup"><span data-stu-id="926dc-111">Use the DATEPART names when you build result sets to be displayed to a user, because the date names are frequently more meaningful than a numeric representation.</span></span> <span data-ttu-id="926dc-112">Однако не следует кодировать какую-либо логику, зависящую от отображаемых названий на том или ином языке.</span><span class="sxs-lookup"><span data-stu-id="926dc-112">However, do not code any logic that depends on the displayed names being from a specific language.</span></span>  
  
-   <span data-ttu-id="926dc-113">При указании дат для сравнения либо ввода с помощью инструкций INSERT или UPDATE следует использовать константы, интерпретируемые одним и тем же образом для всех языковых настроек.</span><span class="sxs-lookup"><span data-stu-id="926dc-113">When you specify dates in comparisons or for input to INSERT or UPDATE statements, use constants that are interpreted the same way for all language settings:</span></span>  
  
    -   <span data-ttu-id="926dc-114">В приложениях ADO, OLE DB и ODBC следует использовать принятые в ODBC форматы отметок времени, даты и времени:</span><span class="sxs-lookup"><span data-stu-id="926dc-114">ADO, OLE DB, and ODBC applications should use the ODBC timestamp, date, and time escape clauses of:</span></span>  
  
         <span data-ttu-id="926dc-115">**{TS '** yyyy **-** _mm_ **-** _ддхх_**:**_mm_**:**_СС_[**.** _FFF_] **'}** Например: **{TS '** 1998 **-** 09 **-** 24 10 **:** 02 **:** 20 **'}**</span><span class="sxs-lookup"><span data-stu-id="926dc-115">**{ ts'** yyyy**-**_mm_**-**_ddhh_**:**_mm_**:**_ss_[**.**_fff_] **'}** such as: **{ ts'** 1998**-** 09**-** 24 10 **:** 02 **:** 20 **' }**</span></span>  
  
         <span data-ttu-id="926dc-116">**{ d'** _гггг_ **-** _мм_ **-** _дд_ **'}** , например: **{ d'** 1998**-** 09**-** 24 **'}**</span><span class="sxs-lookup"><span data-stu-id="926dc-116">**{ d'** _yyyy_ **-** _mm_ **-** _dd_ **'}** such as: **{ d'** 1998**-** 09**-** 24 **'}**</span></span>  
  
         <span data-ttu-id="926dc-117">**{t '** _чч_ **:** _мм_ **:** _СС_ **'}** , например: **{t '** 10:02:20 **'}**</span><span class="sxs-lookup"><span data-stu-id="926dc-117">**{ t'** _hh_ **:** _mm_ **:** _ss_ **'}** such as: **{ t'** 10:02:20 **'}**</span></span>  
  
    -   <span data-ttu-id="926dc-118">В приложениях с использованием других прикладных программных API-интерфейсов, а также в скриптах языка [!INCLUDE[tsql](../../includes/tsql-md.md)] , хранимых процедурах и триггерах следует использовать числовые строки без разделителей.</span><span class="sxs-lookup"><span data-stu-id="926dc-118">Applications that use other APIs, or [!INCLUDE[tsql](../../includes/tsql-md.md)] scripts, stored procedures, and triggers, should use the unseparated numeric strings.</span></span> <span data-ttu-id="926dc-119">Например, *yyyymmdd* в виде 19980924.</span><span class="sxs-lookup"><span data-stu-id="926dc-119">For example, *yyyymmdd* as 19980924.</span></span>  
  
    -   <span data-ttu-id="926dc-120">Приложения, использующие другие API-интерфейсы, [!INCLUDE[tsql](../../includes/tsql-md.md)] скрипты, хранимые процедуры и триггеры, должны использовать инструкцию CONVERT с параметром явного стиля для всех преобразований между типами данных,,,, `time` `date` `smalldate` `datetime` **datetime2**и `datetimeoffset` символьными строковыми типами данных.</span><span class="sxs-lookup"><span data-stu-id="926dc-120">Applications that use other APIs, or [!INCLUDE[tsql](../../includes/tsql-md.md)] scripts, stored procedures, and triggers should use the CONVERT statement with an explicit style parameter for all conversions between the `time`, `date`, `smalldate`, `datetime`, **datetime2**, and `datetimeoffset` data types and character string data types.</span></span> <span data-ttu-id="926dc-121">Например, следующая инструкция интерпретируется одинаково для любых настроек языка и формата даты в соединении:</span><span class="sxs-lookup"><span data-stu-id="926dc-121">For example, the following statement is interpreted in the same way for all language or date format connection settings:</span></span>  
  
        ```  
        SELECT *  
        FROM AdventureWorks2012.Sales.SalesOrderHeader  
        WHERE OrderDate = CONVERT(DATETIME, '20060719', 101)  
        ```  
  
         <span data-ttu-id="926dc-122">Дополнительные сведения см. в разделе [Функции CAST и CONVERT (Transact-SQL)](/sql/t-sql/functions/cast-and-convert-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="926dc-122">For more information, see [CAST and CONVERT &#40;Transact-SQL&#41;](/sql/t-sql/functions/cast-and-convert-transact-sql).</span></span>  
  
  
