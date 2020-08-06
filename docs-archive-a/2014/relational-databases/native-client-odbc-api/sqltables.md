---
title: SQLTables | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
topic_type:
- apiref
helpviewer_keywords:
- SQLTables function
ms.assetid: 77b6c15c-9cf7-4019-b3f0-3d27d23ef656
author: rothja
ms.author: jroth
ms.openlocfilehash: bad60aa102a7771935e37ac963e6fa0d3cb2fd57
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87664168"
---
# <a name="sqltables"></a><span data-ttu-id="2f76c-102">SQLTables</span><span class="sxs-lookup"><span data-stu-id="2f76c-102">SQLTables</span></span>
  <span data-ttu-id="2f76c-103">SQLTables может выполняться на статическом серверном курсоре.</span><span class="sxs-lookup"><span data-stu-id="2f76c-103">SQLTables can be executed on a static server cursor.</span></span> <span data-ttu-id="2f76c-104">Попытка выполнить SQLTables для обновляемого (динамического или ключевого набора ключей) курсора возвратит SQL_SUCCESS_WITH_INFO, указывающее, что тип курсора был изменен.</span><span class="sxs-lookup"><span data-stu-id="2f76c-104">An attempt to execute SQLTables on an updatable (dynamic or keyset) cursor will return SQL_SUCCESS_WITH_INFO indicating that the cursor type has been changed.</span></span>  
  
 <span data-ttu-id="2f76c-105">SQLTables сообщает таблицы из всех баз данных, если параметр *CatalogName* имеет значение SQL_ALL_CATALOGS и все остальные параметры содержат значения по умолчанию (указатели NULL).</span><span class="sxs-lookup"><span data-stu-id="2f76c-105">SQLTables reports tables from all databases when the *CatalogName* parameter is SQL_ALL_CATALOGS and all other parameters contain default values (NULL pointers).</span></span>  
  
 <span data-ttu-id="2f76c-106">Чтобы сообщать о доступных каталогах, схемах и табличных типах, SQLTables позволяет использовать пустые строки (указатели в виде байтов нулевой длины).</span><span class="sxs-lookup"><span data-stu-id="2f76c-106">To report available catalogs, schemas, and table types, SQLTables makes special use of empty strings (zero-length byte pointers).</span></span> <span data-ttu-id="2f76c-107">Пустые строки не являются значениями по умолчанию (указатели NULL).</span><span class="sxs-lookup"><span data-stu-id="2f76c-107">Empty strings are not default values (NULL pointers).</span></span>  
  
 <span data-ttu-id="2f76c-108">Драйвер ODBC для собственного клиента [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] поддерживает выдачу сведений о таблицах, находящихся на связанных серверах, принимая двухкомпонентное имя в параметре *CatalogName* : *Имя_Связанного_Сервера.Имя_Каталога*.</span><span class="sxs-lookup"><span data-stu-id="2f76c-108">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client ODBC driver supports reporting information for tables on linked servers by accepting a two-part name for the *CatalogName* parameter: *Linked_Server_Name.Catalog_Name*.</span></span>  
  
 <span data-ttu-id="2f76c-109">SQLTables возвращает сведения обо всех таблицах, имена которых совпадают с *TableName* и принадлежат текущему пользователю.</span><span class="sxs-lookup"><span data-stu-id="2f76c-109">SQLTables returns information about any tables whose names match *TableName* and are owned by the current user.</span></span>  
  
## <a name="sqltables-and-table-valued-parameters"></a><span data-ttu-id="2f76c-110">Функция SQLTables и возвращающие табличное значение параметры</span><span class="sxs-lookup"><span data-stu-id="2f76c-110">SQLTables and Table-Valued Parameters</span></span>  
 <span data-ttu-id="2f76c-111">Если атрибут инструкции SQL_SOPT_SS_NAME_SCOPE имеет значение SQL_SS_NAME_SCOPE_TABLE_TYPE, а не значение по умолчанию SQL_SS_NAME_SCOPE_TABLE, SQLTables возвращает сведения о табличных типах.</span><span class="sxs-lookup"><span data-stu-id="2f76c-111">When the statement attribute SQL_SOPT_SS_NAME_SCOPE has the value SQL_SS_NAME_SCOPE_TABLE_TYPE, rather than its default value of SQL_SS_NAME_SCOPE_TABLE, SQLTables returns information about table types.</span></span> <span data-ttu-id="2f76c-112">Значение TABLE_TYPE, возвращаемое для табличного типа в столбце 4 результирующего набора, возвращаемого функцией SQLTables, — это ТАБЛИЧный тип.</span><span class="sxs-lookup"><span data-stu-id="2f76c-112">The TABLE_TYPE value returned for a table type in column 4 of the result set returned by SQLTables is TABLE TYPE.</span></span> <span data-ttu-id="2f76c-113">Дополнительные сведения о SQL_SOPT_SS_NAME_SCOPE см. в разделе [SQLSetStmtAttr](sqlsetstmtattr.md).</span><span class="sxs-lookup"><span data-stu-id="2f76c-113">For more information on SQL_SOPT_SS_NAME_SCOPE, see [SQLSetStmtAttr](sqlsetstmtattr.md).</span></span>  
  
 <span data-ttu-id="2f76c-114">Таблицы, представления и синонимы имеют общее пространство имен, отличающееся от пространства имен табличных типов.</span><span class="sxs-lookup"><span data-stu-id="2f76c-114">Tables, views, and synonyms share a common namespace that is distinct from the namespace used by table types.</span></span> <span data-ttu-id="2f76c-115">Хотя таблица и представление не могут иметь одинаковое имя, в одном каталоге и схеме можно иметь таблицу и табличный тип с одинаковым именем.</span><span class="sxs-lookup"><span data-stu-id="2f76c-115">Although it is not possible to have a table and a view with the same name, it is possible to have a table and a table type with the same in the same catalog and schema.</span></span>  
  
 <span data-ttu-id="2f76c-116">Дополнительные сведения о возвращающих табличное значение параметрах см. в разделе [возвращающие табличное значение параметры &#40;ODBC&#41;](../native-client-odbc-table-valued-parameters/table-valued-parameters-odbc.md).</span><span class="sxs-lookup"><span data-stu-id="2f76c-116">For more information about table-valued parameters, see [Table-Valued Parameters &#40;ODBC&#41;](../native-client-odbc-table-valued-parameters/table-valued-parameters-odbc.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="2f76c-117">Пример</span><span class="sxs-lookup"><span data-stu-id="2f76c-117">Example</span></span>  
  
```  
// Get a list of all tables in the current database.  
SQLTables(hstmt, NULL, 0, NULL, 0, NULL, 0, NULL,0);  
  
// Get a list of all tables in all databases.  
SQLTables(hstmt, (SQLCHAR*) "%", SQL_NTS, NULL, 0, NULL, 0, NULL,0);  
  
// Get a list of databases on the current connection's server.  
SQLTables(hstmt, (SQLCHAR*) "%", SQL_NTS, (SQLCHAR*)"", 0, (SQLCHAR*)"",  
    0, NULL, 0);  
```  
  
## <a name="see-also"></a><span data-ttu-id="2f76c-118">См. также:</span><span class="sxs-lookup"><span data-stu-id="2f76c-118">See Also</span></span>  
 <span data-ttu-id="2f76c-119">[Функция SQLTables](https://go.microsoft.com/fwlink/?LinkId=59374) </span><span class="sxs-lookup"><span data-stu-id="2f76c-119">[SQLTables Function](https://go.microsoft.com/fwlink/?LinkId=59374) </span></span>  
 [<span data-ttu-id="2f76c-120">ODBC API Implementation Details</span><span class="sxs-lookup"><span data-stu-id="2f76c-120">ODBC API Implementation Details</span></span>](odbc-api-implementation-details.md)  
  
  
