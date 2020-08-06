---
title: Функции с массовым копированием | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- SQL Server Native Client ODBC driver, bulk copy
- bulk copy [ODBC], functions
- ODBC, bulk copy operations
- functions [ODBC]
ms.assetid: 6526b892-1d58-4f55-8335-f09887f6ea02
author: rothja
ms.author: jroth
ms.openlocfilehash: 02dba8cf4d510d2ec5f20e600302bb692c749f97
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87665317"
---
# <a name="bulk-copy-functions"></a><span data-ttu-id="d85a5-102">Bulk Copy Functions</span><span class="sxs-lookup"><span data-stu-id="d85a5-102">Bulk Copy Functions</span></span>
  <span data-ttu-id="d85a5-103">Зависящее от [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] расширение API-интерфейса массового копирования драйвера ODBC собственного клиента [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] позволяет клиентскому приложению быстро добавлять или извлекать строки данных из таблицы [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="d85a5-103">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]-specific bulk-copy API extension of the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client ODBC driver allows client applications to rapidly add data rows to, or extract data rows from, a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] table.</span></span>  
  
 <span data-ttu-id="d85a5-104">При использовании [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client вы можете ссылаться на функции массового копирования (BCP), объявленные в файлах SQLNCLI11.LIB и SQLNCLI.H.</span><span class="sxs-lookup"><span data-stu-id="d85a5-104">When using [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client, you can reference the bulk copy functions (BCP) in SQLNCLI11.LIB and SQLNCLI.H.</span></span>  
  
 <span data-ttu-id="d85a5-105">Приложение, использующее вызовы функции BCP API, необходимо связать с библиотекой (LIB-файлом), которая поставлялась с драйвером (DLL-файлом), используемым приложением.</span><span class="sxs-lookup"><span data-stu-id="d85a5-105">An application that uses BCP API function calls should link with the library (.lib) that shipped with the driver (.dll) used by the application.</span></span> <span data-ttu-id="d85a5-106">Приложение BCP не должно быть связано более чем с одной библиотекой драйвера.</span><span class="sxs-lookup"><span data-stu-id="d85a5-106">A BCP application should not link with more than one driver library.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="d85a5-107">в этом разделе</span><span class="sxs-lookup"><span data-stu-id="d85a5-107">In This Section</span></span>  
  
-   [<span data-ttu-id="d85a5-108">bcp_batch</span><span class="sxs-lookup"><span data-stu-id="d85a5-108">bcp_batch</span></span>](bcp-batch.md)  
  
-   [<span data-ttu-id="d85a5-109">bcp_bind</span><span class="sxs-lookup"><span data-stu-id="d85a5-109">bcp_bind</span></span>](bcp-bind.md)  
  
-   [<span data-ttu-id="d85a5-110">bcp_colfmt</span><span class="sxs-lookup"><span data-stu-id="d85a5-110">bcp_colfmt</span></span>](bcp-colfmt.md)  
  
-   [<span data-ttu-id="d85a5-111">bcp_collen</span><span class="sxs-lookup"><span data-stu-id="d85a5-111">bcp_collen</span></span>](bcp-collen.md)  
  
-   [<span data-ttu-id="d85a5-112">bcp_colptr</span><span class="sxs-lookup"><span data-stu-id="d85a5-112">bcp_colptr</span></span>](bcp-colptr.md)  
  
-   [<span data-ttu-id="d85a5-113">bcp_columns</span><span class="sxs-lookup"><span data-stu-id="d85a5-113">bcp_columns</span></span>](bcp-columns.md)  
  
-   [<span data-ttu-id="d85a5-114">bcp_control</span><span class="sxs-lookup"><span data-stu-id="d85a5-114">bcp_control</span></span>](bcp-control.md)  
  
-   [<span data-ttu-id="d85a5-115">bcp_done</span><span class="sxs-lookup"><span data-stu-id="d85a5-115">bcp_done</span></span>](bcp-done.md)  
  
-   [<span data-ttu-id="d85a5-116">bcp_exec</span><span class="sxs-lookup"><span data-stu-id="d85a5-116">bcp_exec</span></span>](bcp-exec.md)  
  
-   [<span data-ttu-id="d85a5-117">bcp_getcolfmt</span><span class="sxs-lookup"><span data-stu-id="d85a5-117">bcp_getcolfmt</span></span>](bcp-getcolfmt.md)  
  
-   [<span data-ttu-id="d85a5-118">bcp_gettypename</span><span class="sxs-lookup"><span data-stu-id="d85a5-118">bcp_gettypename</span></span>](bcp-gettypename.md)  
  
-   [<span data-ttu-id="d85a5-119">bcp_init</span><span class="sxs-lookup"><span data-stu-id="d85a5-119">bcp_init</span></span>](bcp-init.md)  
  
-   [<span data-ttu-id="d85a5-120">bcp_moretext</span><span class="sxs-lookup"><span data-stu-id="d85a5-120">bcp_moretext</span></span>](bcp-moretext.md)  
  
-   [<span data-ttu-id="d85a5-121">bcp_readfmt</span><span class="sxs-lookup"><span data-stu-id="d85a5-121">bcp_readfmt</span></span>](bcp-readfmt.md)  
  
-   [<span data-ttu-id="d85a5-122">bcp_sendrow</span><span class="sxs-lookup"><span data-stu-id="d85a5-122">bcp_sendrow</span></span>](bcp-sendrow.md)  
  
-   [<span data-ttu-id="d85a5-123">bcp_setbulkmode</span><span class="sxs-lookup"><span data-stu-id="d85a5-123">bcp_setbulkmode</span></span>](bcp-setbulkmode.md)  
  
-   [<span data-ttu-id="d85a5-124">bcp_setcolfmt</span><span class="sxs-lookup"><span data-stu-id="d85a5-124">bcp_setcolfmt</span></span>](bcp-setcolfmt.md)  
  
-   [<span data-ttu-id="d85a5-125">Функция bcp_writefmt</span><span class="sxs-lookup"><span data-stu-id="d85a5-125">bcp_writefmt</span></span>](bcp-writefmt.md)  
  
## <a name="see-also"></a><span data-ttu-id="d85a5-126">См. также:</span><span class="sxs-lookup"><span data-stu-id="d85a5-126">See Also</span></span>  
 <span data-ttu-id="d85a5-127">[Расширения драйверов SQL Server](../../database-engine/dev-guide/sql-server-driver-extensions.md) </span><span class="sxs-lookup"><span data-stu-id="d85a5-127">[SQL Server Driver Extensions](../../database-engine/dev-guide/sql-server-driver-extensions.md) </span></span>  
 [<span data-ttu-id="d85a5-128">Выполнение операций с массовым копированием &#40;ODBC&#41;</span><span class="sxs-lookup"><span data-stu-id="d85a5-128">Performing Bulk Copy Operations &#40;ODBC&#41;</span></span>](../native-client-odbc-bulk-copy-operations/performing-bulk-copy-operations-odbc.md)  
  
  
