---
title: Поддержка FILESTREAM | Документация Майкрософт
ms.custom: ''
ms.date: 04/27/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- FILESTREAM [SQL Server], SQL Server Native Client
- SQL Server Native Client [FILESTREAM support]
ms.assetid: 1ad3400d-7fcd-40c9-87ae-f5afc61e0374
author: rothja
ms.author: jroth
ms.openlocfilehash: 18e9a002bfb205e2c0807234550998fe48120d20
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87730601"
---
# <a name="filestream-support"></a><span data-ttu-id="c99fd-102">Поддержка FILESTREAM</span><span class="sxs-lookup"><span data-stu-id="c99fd-102">FILESTREAM Support</span></span>
  <span data-ttu-id="c99fd-103">Компонент FILESTREAM предоставляет способ хранения и доступа к большим двоичным значениям либо с помощью [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)], либо путем непосредственного доступа к файловой системе Windows.</span><span class="sxs-lookup"><span data-stu-id="c99fd-103">FILESTREAM provides a way to store and access large binary values, either through [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] or by direct access to the Windows file system.</span></span> <span data-ttu-id="c99fd-104">Большим двоичным значением считается значение с размером больше 2 гигабайт (ГБ).</span><span class="sxs-lookup"><span data-stu-id="c99fd-104">A large binary value is a value larger than 2 gigabytes (GB).</span></span> <span data-ttu-id="c99fd-105">Дополнительные сведения о поддержке усовершенствованного компонента FILESTREAM см. в статье [FILESTREAM (SQL Server)](../../blob/filestream-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="c99fd-105">For more information about enhanced FILESTREAM support, see [FILESTREAM &#40;SQL Server&#41;](../../blob/filestream-sql-server.md).</span></span>  
  
 <span data-ttu-id="c99fd-106">После открытия подключения к базе данных параметр `@@TEXTSIZE` устанавливается в значение -1 («неограниченный») по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="c99fd-106">When a database connection is opened, `@@TEXTSIZE` will be set to -1 ("unlimited"), by default.</span></span>  
  
 <span data-ttu-id="c99fd-107">Предусмотрена также возможность получения доступа и обновления столбцов FILESTREAM с помощью API файловой системы Windows.</span><span class="sxs-lookup"><span data-stu-id="c99fd-107">It is also possible to access and update FILESTREAM columns using Windows file system APIs.</span></span>  
  
 <span data-ttu-id="c99fd-108">Дополнительные сведения см. в следующих разделах:</span><span class="sxs-lookup"><span data-stu-id="c99fd-108">For more information, see the following topics:</span></span>  
  
-   [<span data-ttu-id="c99fd-109">Поддержка FILESTREAM &#40;OLE DB&#41;</span><span class="sxs-lookup"><span data-stu-id="c99fd-109">FILESTREAM Support &#40;OLE DB&#41;</span></span>](../ole-db/filestream-support-ole-db.md)  
  
-   [<span data-ttu-id="c99fd-110">Поддержка FILESTREAM &#40;ODBC&#41;</span><span class="sxs-lookup"><span data-stu-id="c99fd-110">FILESTREAM Support &#40;ODBC&#41;</span></span>](../odbc/filestream-support-odbc.md)  
  
-   [<span data-ttu-id="c99fd-111">Доступ к данным FILESTREAM с OpenSqlFilestream</span><span class="sxs-lookup"><span data-stu-id="c99fd-111">Access FILESTREAM Data with OpenSqlFilestream</span></span>](../../blob/access-filestream-data-with-opensqlfilestream.md)  
  
## <a name="querying-for-filestream-columns"></a><span data-ttu-id="c99fd-112">Запрос столбцов FILESTREAM</span><span class="sxs-lookup"><span data-stu-id="c99fd-112">Querying for FILESTREAM Columns</span></span>  
 <span data-ttu-id="c99fd-113">Наборы строк схемы в OLE DB не сообщают, является ли столбец столбцом FILESTREAM.</span><span class="sxs-lookup"><span data-stu-id="c99fd-113">Schema rowsets in OLE DB will not report whether a column is a FILESTREAM column.</span></span> <span data-ttu-id="c99fd-114">Для создания столбца FILESTREAM невозможно использовать интерфейс ITableDefinition в OLE DB.</span><span class="sxs-lookup"><span data-stu-id="c99fd-114">ITableDefinition in OLE DB cannot be used to create a FILESTREAM column.</span></span>  
  
 <span data-ttu-id="c99fd-115">Функции каталога, такие как SQLColumns в ODBC, не сообщают о том, является ли столбец столбцом FILESTREAM.</span><span class="sxs-lookup"><span data-stu-id="c99fd-115">Catalog functions such as SQLColumns in ODBC will not report whether a column is a FILESTREAM column.</span></span>  
  
 <span data-ttu-id="c99fd-116">Чтобы создать столбцы FILESTREAM или определить, какие существующие столбцы являются столбцами FILESTREAM, можно использовать `is_filestream` Столбец представления каталога [sys. Columns](/sql/relational-databases/system-catalog-views/sys-columns-transact-sql) .</span><span class="sxs-lookup"><span data-stu-id="c99fd-116">To create FILESTREAM columns or to detect which existing columns are FILESTREAM columns, you can use the `is_filestream` column of the [sys.columns](/sql/relational-databases/system-catalog-views/sys-columns-transact-sql) catalog view.</span></span>  
  
 <span data-ttu-id="c99fd-117">Ниже представлен пример такого кода.</span><span class="sxs-lookup"><span data-stu-id="c99fd-117">The following is an example:</span></span>  
  
```  
-- Create a table with a FILESTREAM column.  
CREATE TABLE Bob_01 (GuidCol1 uniqueidentifier ROWGUIDCOL NOT NULL UNIQUE DEFAULT NEWID(), IntCol2 int, varbinaryCol3 varbinary(max) FILESTREAM);  
  
-- Find FILESTREAM columns.  
SELECT name FROM sys.columns WHERE is_filestream=1;  
  
-- Determine whether a column is a FILESTREAM column.  
SELECT is_filestream FROM sys.columns WHERE name = 'varbinaryCol3' AND object_id IN (SELECT object_id FROM sys.tables WHERE name='Bob_01');  
```  
  
## <a name="down-level-compatibility"></a><span data-ttu-id="c99fd-118">Совместимость на низком уровне</span><span class="sxs-lookup"><span data-stu-id="c99fd-118">Down-Level Compatibility</span></span>  
 <span data-ttu-id="c99fd-119">Если клиент был скомпилирован с использованием версии [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] собственного клиента, которая была включена в [!INCLUDE[ssVersion2005](../../../includes/sscurrent-md.md)] , `varbinary(max)` поведение будет совместимо с [!INCLUDE[ssVersion2005](../../../includes/ssversion2005-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="c99fd-119">If your client was compiled using the version of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client that was included with [!INCLUDE[ssVersion2005](../../../includes/sscurrent-md.md)], `varbinary(max)` behavior will be compatible with [!INCLUDE[ssVersion2005](../../../includes/ssversion2005-md.md)].</span></span> <span data-ttu-id="c99fd-120">Это означает, что максимальный размер возвращаемых данных будет ограничен 2 ГБ.</span><span class="sxs-lookup"><span data-stu-id="c99fd-120">That is, the maximum size of returned data will be limited to 2 GB.</span></span> <span data-ttu-id="c99fd-121">Для результирующих значений больше 2 ГБ произойдет усечение, и будет возвращено сообщение "Усечение строковых данных справа".</span><span class="sxs-lookup"><span data-stu-id="c99fd-121">For result values larger that 2 GB, truncation will occur and a "string data right truncation" warning will be returned.</span></span>  
  
 <span data-ttu-id="c99fd-122">Если уровень совместимости типов данных установлен равным «80», то поведение клиента будет согласовано с поведением клиента низкого уровня.</span><span class="sxs-lookup"><span data-stu-id="c99fd-122">When data-type compatibility is set to 80, client behavior will be consistent with down-level client behavior.</span></span>  
  
 <span data-ttu-id="c99fd-123">Для клиентов, которые используют SQLOLEDB или другие поставщики, выпущенные до [!INCLUDE[ssVersion2005](../../../includes/ssnoversion-md.md)] собственного клиента, `varbinary(max)` будут сопоставлены с изображением.</span><span class="sxs-lookup"><span data-stu-id="c99fd-123">For clients that use SQLOLEDB or other providers that were released before the [!INCLUDE[ssVersion2005](../../../includes/ssnoversion-md.md)] Native Client, `varbinary(max)` will be mapped to image.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c99fd-124">См. также:</span><span class="sxs-lookup"><span data-stu-id="c99fd-124">See Also</span></span>  
 [<span data-ttu-id="c99fd-125">Компоненты собственного клиента SQL Server</span><span class="sxs-lookup"><span data-stu-id="c99fd-125">SQL Server Native Client Features</span></span>](sql-server-native-client-features.md)  
  
  
