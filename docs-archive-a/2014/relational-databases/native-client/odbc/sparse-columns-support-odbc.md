---
title: Поддержка разреженных столбцов (ODBC) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
ms.assetid: 11ae959f-2fb6-4b85-ac5d-1476a82136d4
author: rothja
ms.author: jroth
ms.openlocfilehash: 076709f3f37e92492f7c3f8c20ee692416d9e867
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87734025"
---
# <a name="sparse-columns-support-odbc"></a><span data-ttu-id="27bcc-102">Поддержка разреженных столбцов (ODBC)</span><span class="sxs-lookup"><span data-stu-id="27bcc-102">Sparse Columns Support (ODBC)</span></span>
  <span data-ttu-id="27bcc-103">В этом разделе описывается поддержка разреженных столбцов драйвером ODBC для собственного клиента [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="27bcc-103">This topic describes [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client ODBC support for sparse columns.</span></span> <span data-ttu-id="27bcc-104">Пример, демонстрирующий поддержку ODBC для разреженных столбцов, см. в разделе [вызов SQLColumns для таблицы с разреженными столбцами](../../native-client-odbc-how-to/call-sqlcolumns-on-a-table-with-sparse-columns.md).</span><span class="sxs-lookup"><span data-stu-id="27bcc-104">For a sample demonstrating ODBC support for sparse columns, see [Call SQLColumns on a Table with Sparse Columns](../../native-client-odbc-how-to/call-sqlcolumns-on-a-table-with-sparse-columns.md).</span></span> <span data-ttu-id="27bcc-105">Дополнительные сведения о разреженных столбцах см. [в разделе Поддержка разреженных столбцов в SQL Server Native Client](../features/sparse-columns-support-in-sql-server-native-client.md).</span><span class="sxs-lookup"><span data-stu-id="27bcc-105">For more information about sparse columns, see [Sparse Columns Support in SQL Server Native Client](../features/sparse-columns-support-in-sql-server-native-client.md).</span></span>  
  
## <a name="statement-metadata"></a><span data-ttu-id="27bcc-106">Метаданные инструкции</span><span class="sxs-lookup"><span data-stu-id="27bcc-106">Statement Metadata</span></span>  
 <span data-ttu-id="27bcc-107">Поле дескриптора в дескрипторе параметра приложения (APD) и атрибут инструкции SQL_SOPT_SS_NAME_SCOPE принимают дополнительные значения SQL_SS_NAME_SCOPE_EXTENDED и SQL_SS_NAME_SCOPE_SPARSE_COLUMN_SET.</span><span class="sxs-lookup"><span data-stu-id="27bcc-107">The application parameter descriptor (APD) descriptor field and SQL_SOPT_SS_NAME_SCOPE statement attribute accepts the additional values SQL_SS_NAME_SCOPE_EXTENDED and SQL_SS_NAME_SCOPE_SPARSE_COLUMN_SET.</span></span> <span data-ttu-id="27bcc-108">Эти значения определяют, какие столбцы включаются в возвращаемый [SQLColumns](../../native-client-odbc-api/sqlcolumns.md)результирующий набор.</span><span class="sxs-lookup"><span data-stu-id="27bcc-108">These values specify which columns are included in the result set returned by [SQLColumns](../../native-client-odbc-api/sqlcolumns.md).</span></span> <span data-ttu-id="27bcc-109">Дополнительные сведения об атрибуте SQL_SOPT_SS_NAME_SCOPE см. в разделе [SQLSetStmtAttr](../../native-client-odbc-api/sqlsetstmtattr.md).</span><span class="sxs-lookup"><span data-stu-id="27bcc-109">For more information about SQL_SOPT_SS_NAME_SCOPE, see [SQLSetStmtAttr](../../native-client-odbc-api/sqlsetstmtattr.md).</span></span>  
  
 <span data-ttu-id="27bcc-110">Новый дескриптор строки реализации (IRD), доступное только для чтения поле SQL_CA_SS_IS_COLUMN_SET типа SQLSMALLINT, позволяет определить, имеет ли столбец значение XML `column_set`.</span><span class="sxs-lookup"><span data-stu-id="27bcc-110">A new implementation row descriptor (IRD), a read-only SQLSMALLINT field called SQL_CA_SS_IS_COLUMN_SET, can be used to determine if a column is an XML `column_set` value.</span></span> <span data-ttu-id="27bcc-111">SQL_CA_SS_IS_COLUMN_SET принимает значения SQL_TRUE and SQL_FALSE.</span><span class="sxs-lookup"><span data-stu-id="27bcc-111">SQL_CA_SS_IS_COLUMN_SET takes the values SQL_TRUE and SQL_FALSE.</span></span>  
  
## <a name="catalog-metadata"></a><span data-ttu-id="27bcc-112">Метаданные каталога</span><span class="sxs-lookup"><span data-stu-id="27bcc-112">Catalog Metadata</span></span>  
 <span data-ttu-id="27bcc-113">В [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] в результирующий набор для [SQLColumns](../../native-client-odbc-api/sqlcolumns.md).</span><span class="sxs-lookup"><span data-stu-id="27bcc-113">Two [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] specific columns (SS_IS_SPARSE and SS_IS_COLUMN_SET) have been added to the result set for [SQLColumns](../../native-client-odbc-api/sqlcolumns.md).</span></span>  
  
## <a name="odbc-function-support-for-sparse-columns"></a><span data-ttu-id="27bcc-114">Поддержка функций ODBC для разреженных столбцов</span><span class="sxs-lookup"><span data-stu-id="27bcc-114">ODBC Function Support for Sparse Columns</span></span>  
 <span data-ttu-id="27bcc-115">Следующие функции ODBC были обновлены для поддержки разреженных столбцов в собственном клиенте [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] :</span><span class="sxs-lookup"><span data-stu-id="27bcc-115">The following ODBC functions have been updated to support sparse columns in [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client:</span></span>  
  
-   [<span data-ttu-id="27bcc-116">SQLColAttribute</span><span class="sxs-lookup"><span data-stu-id="27bcc-116">SQLColAttribute</span></span>](../../native-client-odbc-api/sqlcolattribute.md)  
  
-   [<span data-ttu-id="27bcc-117">SQLColumns</span><span class="sxs-lookup"><span data-stu-id="27bcc-117">SQLColumns</span></span>](../../native-client-odbc-api/sqlcolumns.md)  
  
-   [<span data-ttu-id="27bcc-118">SQLGetDescField</span><span class="sxs-lookup"><span data-stu-id="27bcc-118">SQLGetDescField</span></span>](../../native-client-odbc-api/sqlgetdescfield.md)  
  
-   [<span data-ttu-id="27bcc-119">SQLSetDescField</span><span class="sxs-lookup"><span data-stu-id="27bcc-119">SQLSetDescField</span></span>](../../native-client-odbc-api/sqlsetdescfield.md)  
  
-   [<span data-ttu-id="27bcc-120">SQLSetStmtAttr</span><span class="sxs-lookup"><span data-stu-id="27bcc-120">SQLSetStmtAttr</span></span>](../../native-client-odbc-api/sqlsetstmtattr.md)  
  
## <a name="see-also"></a><span data-ttu-id="27bcc-121">См. также:</span><span class="sxs-lookup"><span data-stu-id="27bcc-121">See Also</span></span>  
 [<span data-ttu-id="27bcc-122">SQL Server Native Client (ODBC)</span><span class="sxs-lookup"><span data-stu-id="27bcc-122">SQL Server Native Client &#40;ODBC&#41;</span></span>](sql-server-native-client-odbc.md)  
  
  
