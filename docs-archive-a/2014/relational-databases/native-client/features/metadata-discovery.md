---
title: Обнаружение метаданных | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
ms.assetid: ec3c0f4f-f838-43ce-85f2-cf2761e2aac5
author: rothja
ms.author: jroth
ms.openlocfilehash: 571df9f21ab46a53c8aba7907039ce02afd6ad05
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87730586"
---
# <a name="metadata-discovery"></a><span data-ttu-id="ca5ee-102">Обнаружение метаданных</span><span class="sxs-lookup"><span data-stu-id="ca5ee-102">Metadata Discovery</span></span>
  <span data-ttu-id="ca5ee-103">Улучшение обнаружения метаданных в [!INCLUDE[ssSQL11](../../../includes/sssql11-md.md)] позволяет [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] собственным клиентским приложениям гарантировать, что метаданные столбца или параметра, возвращаемые при выполнении запроса, идентичны или совместимы с форматом метаданных, указанным перед выполнением запроса.</span><span class="sxs-lookup"><span data-stu-id="ca5ee-103">The metadata discovery improvement in [!INCLUDE[ssSQL11](../../../includes/sssql11-md.md)] allows [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client applications to ensure that column or parameter metadata returned from the execution of a query is identical to or compatible with the metadata format you specified before you executed the query.</span></span> <span data-ttu-id="ca5ee-104">Если формат метаданных, возвращенных в результате выполнения запроса, будет несовместим с форматом, указанным до выполнения запроса, возвращается ошибка.</span><span class="sxs-lookup"><span data-stu-id="ca5ee-104">You will receive an error if the metadata returned after query execution is not compatible with the metadata format you specified before query execution.</span></span>  
  
 <span data-ttu-id="ca5ee-105">В функциях bcp и ODBC, а также интерфейсах IBCPSession и IBCPSession2 теперь можно задавать отложенное чтение (отложенное обнаружение метаданных), чтобы избежать обнаружения метаданных для операций с параметром queryout.</span><span class="sxs-lookup"><span data-stu-id="ca5ee-105">In bcp and ODBC functions, and IBCPSession and IBCPSession2 interfaces, you can now specify a delayed read (delayed metadata discovery) to avoid metadata discovery for query out operations.</span></span> <span data-ttu-id="ca5ee-106">Это позволяет повысить производительность и устранить ошибки обнаружения метаданных.</span><span class="sxs-lookup"><span data-stu-id="ca5ee-106">This improves performance and eliminates metadata discovery failures.</span></span>  
  
 <span data-ttu-id="ca5ee-107">Если приложение разрабатывается с помощью [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] собственного клиента в [!INCLUDE[ssSQL11](../../../includes/sssql11-md.md)] , но соединение с версией сервера, более ранней [!INCLUDE[ssSQL11](../../../includes/sssql11-md.md)] , чем, функция обнаружения метаданных будет соответствовать версии сервера.</span><span class="sxs-lookup"><span data-stu-id="ca5ee-107">If you develop an application using [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client in [!INCLUDE[ssSQL11](../../../includes/sssql11-md.md)] but connect to a server version earlier than [!INCLUDE[ssSQL11](../../../includes/sssql11-md.md)], metadata discovery functionality will correspond to the version of the server.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ca5ee-108">Remarks</span><span class="sxs-lookup"><span data-stu-id="ca5ee-108">Remarks</span></span>  
 <span data-ttu-id="ca5ee-109">В [!INCLUDE[ssSQL11](../../../includes/sssql11-md.md)] были изменены следующие функции bcp, которые теперь обеспечивают улучшенное обнаружение метаданных:</span><span class="sxs-lookup"><span data-stu-id="ca5ee-109">The following bcp functions have been enhanced in [!INCLUDE[ssSQL11](../../../includes/sssql11-md.md)] to provide improved metadata discovery:</span></span>  
  
-   [<span data-ttu-id="ca5ee-110">bcp_columns</span><span class="sxs-lookup"><span data-stu-id="ca5ee-110">bcp_columns</span></span>](../../native-client-odbc-extensions-bulk-copy-functions/bcp-columns.md)  
  
-   [<span data-ttu-id="ca5ee-111">bcp_control</span><span class="sxs-lookup"><span data-stu-id="ca5ee-111">bcp_control</span></span>](../../native-client-odbc-extensions-bulk-copy-functions/bcp-control.md)  
  
-   [<span data-ttu-id="ca5ee-112">bcp_getcolfmt</span><span class="sxs-lookup"><span data-stu-id="ca5ee-112">bcp_getcolfmt</span></span>](../../native-client-odbc-extensions-bulk-copy-functions/bcp-getcolfmt.md)  
  
-   [<span data-ttu-id="ca5ee-113">bcp_readfmt</span><span class="sxs-lookup"><span data-stu-id="ca5ee-113">bcp_readfmt</span></span>](../../native-client-odbc-extensions-bulk-copy-functions/bcp-readfmt.md)  
  
-   [<span data-ttu-id="ca5ee-114">bcp_setcolfmt</span><span class="sxs-lookup"><span data-stu-id="ca5ee-114">bcp_setcolfmt</span></span>](../../native-client-odbc-extensions-bulk-copy-functions/bcp-setcolfmt.md)  
  
 <span data-ttu-id="ca5ee-115">При указании формата метаданных с помощью [bcp_setbulkmode](../../native-client-odbc-extensions-bulk-copy-functions/bcp-setbulkmode.md)также отображается улучшение производительности.</span><span class="sxs-lookup"><span data-stu-id="ca5ee-115">You will also see a performance improvement when specifying metadata format using [bcp_setbulkmode](../../native-client-odbc-extensions-bulk-copy-functions/bcp-setbulkmode.md).</span></span>  
  
 <span data-ttu-id="ca5ee-116">[bcp_control](../../native-client-odbc-extensions-bulk-copy-functions/bcp-control.md) имеет новый *eOption* для управления поведением bcp_readfmt: `BCPDELAYREADFMT` .</span><span class="sxs-lookup"><span data-stu-id="ca5ee-116">[bcp_control](../../native-client-odbc-extensions-bulk-copy-functions/bcp-control.md) has a new *eOption* to control the behavior of bcp_readfmt: `BCPDELAYREADFMT`.</span></span>  
  
 <span data-ttu-id="ca5ee-117">В [!INCLUDE[ssSQL11](../../../includes/sssql11-md.md)] были изменены следующие функции ODBC, которые теперь обеспечивают улучшенное обнаружение метаданных:</span><span class="sxs-lookup"><span data-stu-id="ca5ee-117">The following ODBC functions have been enhanced in [!INCLUDE[ssSQL11](../../../includes/sssql11-md.md)] to provide improved metadata discovery:</span></span>  
  
-   [<span data-ttu-id="ca5ee-118">SQLNumResultCols</span><span class="sxs-lookup"><span data-stu-id="ca5ee-118">SQLNumResultCols</span></span>](../../native-client-odbc-api/sqlnumresultcols.md)  
  
-   [<span data-ttu-id="ca5ee-119">SQLDescribeCol</span><span class="sxs-lookup"><span data-stu-id="ca5ee-119">SQLDescribeCol</span></span>](../../native-client-odbc-api/sqldescribecol.md)  
  
-   [<span data-ttu-id="ca5ee-120">SQLNumParams</span><span class="sxs-lookup"><span data-stu-id="ca5ee-120">SQLNumParams</span></span>](../../native-client-odbc-api/sqlnumparams.md)  
  
-   [<span data-ttu-id="ca5ee-121">SQLDescribeParam</span><span class="sxs-lookup"><span data-stu-id="ca5ee-121">SQLDescribeParam</span></span>](../../native-client-odbc-api/sqldescribeparam.md)  
  
 <span data-ttu-id="ca5ee-122">В [!INCLUDE[ssSQL11](../../../includes/sssql11-md.md)] были изменены следующие методы OLE DB, которые теперь обеспечивают улучшенное обнаружение метаданных:</span><span class="sxs-lookup"><span data-stu-id="ca5ee-122">The following OLE DB member functions have been enhanced in [!INCLUDE[ssSQL11](../../../includes/sssql11-md.md)] to provide improved metadata discovery:</span></span>  
  
-   <span data-ttu-id="ca5ee-123">IColumnsInfo::GetColumnInfo</span><span class="sxs-lookup"><span data-stu-id="ca5ee-123">IColumnsInfo::GetColumnInfo</span></span>  
  
-   <span data-ttu-id="ca5ee-124">IColumnsRowset::GetColumnsRowset</span><span class="sxs-lookup"><span data-stu-id="ca5ee-124">IColumnsRowset::GetColumnsRowset</span></span>  
  
-   <span data-ttu-id="ca5ee-125">ICommandWithParameters::GetParameterInfo (дополнительные сведения см. в разделе документации [ICommandWithParameters](../../native-client-ole-db-interfaces/icommandwithparameters.md)).</span><span class="sxs-lookup"><span data-stu-id="ca5ee-125">ICommandWithParameters::GetParameterInfo (see [ICommandWithParameters](../../native-client-ole-db-interfaces/icommandwithparameters.md) for more information)</span></span>  
  
 <span data-ttu-id="ca5ee-126">Повышение производительности также заметно при указании формата метаданных с помощью метода IBCPSession::BCPSetBulkMode.</span><span class="sxs-lookup"><span data-stu-id="ca5ee-126">You will also see a performance improvement when specifying metadata format using IBCPSession::BCPSetBulkMode</span></span>  
  
 <span data-ttu-id="ca5ee-127">Улучшенное обнаружение метаданных в собственном клиенте [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] стало возможным благодаря добавлению в [!INCLUDE[ssSQL11](../../../includes/sssql11-md.md)] двух хранимых процедур:</span><span class="sxs-lookup"><span data-stu-id="ca5ee-127">The improved metadata discovery in [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client is possible because of the addition of two stored procedures in [!INCLUDE[ssSQL11](../../../includes/sssql11-md.md)]:</span></span>  
  
-   <span data-ttu-id="ca5ee-128">sp_describe_first_result_set</span><span class="sxs-lookup"><span data-stu-id="ca5ee-128">sp_describe_first_result_set</span></span>  
  
-   <span data-ttu-id="ca5ee-129">sp_describe_undeclared_parameters</span><span class="sxs-lookup"><span data-stu-id="ca5ee-129">sp_describe_undeclared_parameters</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ca5ee-130">См. также:</span><span class="sxs-lookup"><span data-stu-id="ca5ee-130">See Also</span></span>  
 [<span data-ttu-id="ca5ee-131">Компоненты собственного клиента SQL Server</span><span class="sxs-lookup"><span data-stu-id="ca5ee-131">SQL Server Native Client Features</span></span>](sql-server-native-client-features.md)  
  
  
