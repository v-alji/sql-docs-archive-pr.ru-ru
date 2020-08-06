---
title: SQLPrimaryKeys | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
topic_type:
- apiref
helpviewer_keywords:
- SQLPrimaryKeys function
ms.assetid: bc61cd5b-d2f4-4f87-abc7-743cf9ea772d
author: rothja
ms.author: jroth
ms.openlocfilehash: 67a932996ccbf52f5ab21fd6aa62381184ebc510
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87668279"
---
# <a name="sqlprimarykeys"></a><span data-ttu-id="6c00e-102">SQLPrimaryKeys</span><span class="sxs-lookup"><span data-stu-id="6c00e-102">SQLPrimaryKeys</span></span>
  <span data-ttu-id="6c00e-103">Таблица может содержать столбец или столбцы, которые могут использоваться в качестве уникальных идентификаторов строк, а таблицы, созданные без ограничения ПЕРВИЧного ключа, возвращают пустой результирующий набор для SQLPrimaryKeys.</span><span class="sxs-lookup"><span data-stu-id="6c00e-103">A table might have a column or columns that can serve as unique row identifiers, and tables created without a PRIMARY KEY constraint return an empty result set to SQLPrimaryKeys.</span></span> <span data-ttu-id="6c00e-104">Функция ODBC [SQLSpecialColumns](sqlspecialcolumns.md) сообщает кандидатов идентификаторов строк для таблиц без первичных ключей.</span><span class="sxs-lookup"><span data-stu-id="6c00e-104">The ODBC function [SQLSpecialColumns](sqlspecialcolumns.md) reports row identifier candidates for tables without primary keys.</span></span>  
  
 <span data-ttu-id="6c00e-105">SQLPrimaryKeys возвращает SQL_SUCCESS, существуют ли значения для параметров *CatalogName*, *SchemaName*или *TableName* .</span><span class="sxs-lookup"><span data-stu-id="6c00e-105">SQLPrimaryKeys returns SQL_SUCCESS whether or not values exist for *CatalogName*, *SchemaName*, or *TableName* parameters.</span></span> <span data-ttu-id="6c00e-106">Функция SQLFetch возвращает значение SQL_NO_DATA, если в этих параметрах заданы недопустимые значения.</span><span class="sxs-lookup"><span data-stu-id="6c00e-106">SQLFetch returns SQL_NO_DATA when invalid values are used in these parameters.</span></span>  
  
 <span data-ttu-id="6c00e-107">SQLPrimaryKeys может выполняться на статическом серверном курсоре.</span><span class="sxs-lookup"><span data-stu-id="6c00e-107">SQLPrimaryKeys can be executed on a static server cursor.</span></span> <span data-ttu-id="6c00e-108">Попытка выполнить SQLPrimaryKeys для обновляемого (динамического или ключевого набора ключей) курсора возвратит SQL_SUCCESS_WITH_INFO, указывающее, что тип курсора был изменен.</span><span class="sxs-lookup"><span data-stu-id="6c00e-108">An attempt to execute SQLPrimaryKeys on an updatable (dynamic or keyset) cursor will return SQL_SUCCESS_WITH_INFO indicating that the cursor type has been changed.</span></span>  
  
 <span data-ttu-id="6c00e-109">Драйвер ODBC для собственного клиента [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] поддерживает выдачу сведений о таблицах, находящихся на связанных серверах, принимая двухкомпонентное имя в параметре *CatalogName* : *Имя_Связанного_Сервера.Имя_Каталога*.</span><span class="sxs-lookup"><span data-stu-id="6c00e-109">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client ODBC driver supports reporting information for tables on linked servers by accepting a two-part name for the *CatalogName* parameter: *Linked_Server_Name.Catalog_Name*.</span></span>  
  
## <a name="sqlprimarykeys-and-table-valued-parameters"></a><span data-ttu-id="6c00e-110">Функция SQLPrimaryKeys и возвращающие табличные значения параметры</span><span class="sxs-lookup"><span data-stu-id="6c00e-110">SQLPrimaryKeys and Table-Valued Parameters</span></span>  
 <span data-ttu-id="6c00e-111">Если атрибут инструкции SQL_SOPT_SS_NAME_SCOPE имеет значение SQL_SS_NAME_SCOPE_TABLE_TYPE, а не значение по умолчанию SQL_SS_NAME_SCOPE_TABLE, SQLPrimaryKeys будет возвращать сведения о первичных ключевых столбцах табличных типов.</span><span class="sxs-lookup"><span data-stu-id="6c00e-111">If the statement attribute SQL_SOPT_SS_NAME_SCOPE has the value SQL_SS_NAME_SCOPE_TABLE_TYPE, rather than its default value of SQL_SS_NAME_SCOPE_TABLE, SQLPrimaryKeys will return information about primary key columns of table types.</span></span> <span data-ttu-id="6c00e-112">Дополнительные сведения о SQL_SOPT_SS_NAME_SCOPE см. в разделе [SQLSetStmtAttr](sqlsetstmtattr.md).</span><span class="sxs-lookup"><span data-stu-id="6c00e-112">For more information on SQL_SOPT_SS_NAME_SCOPE, see [SQLSetStmtAttr](sqlsetstmtattr.md).</span></span>  
  
 <span data-ttu-id="6c00e-113">Дополнительные сведения о возвращающих табличное значение параметрах см. в разделе [возвращающие табличное значение параметры &#40;ODBC&#41;](../native-client-odbc-table-valued-parameters/table-valued-parameters-odbc.md).</span><span class="sxs-lookup"><span data-stu-id="6c00e-113">For more information about table-valued parameters, see [Table-Valued Parameters &#40;ODBC&#41;](../native-client-odbc-table-valued-parameters/table-valued-parameters-odbc.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6c00e-114">См. также:</span><span class="sxs-lookup"><span data-stu-id="6c00e-114">See Also</span></span>  
 <span data-ttu-id="6c00e-115">[Функция SQLPrimaryKeys](https://go.microsoft.com/fwlink/?LinkId=59361) </span><span class="sxs-lookup"><span data-stu-id="6c00e-115">[SQLPrimaryKeys Function](https://go.microsoft.com/fwlink/?LinkId=59361) </span></span>  
 [<span data-ttu-id="6c00e-116">ODBC API Implementation Details</span><span class="sxs-lookup"><span data-stu-id="6c00e-116">ODBC API Implementation Details</span></span>](odbc-api-implementation-details.md)  
  
  
