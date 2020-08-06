---
title: Использование функций каталога | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- ODBC, functions
- SQLLinkedCatalogs function
- SQL Server Native Client ODBC driver, catalog functions
- SQLLinkedServers function
- catalog functions [ODBC]
- functions [ODBC]
ms.assetid: 7773fb2e-06b5-4c4b-88e9-0ad9132ad273
author: rothja
ms.author: jroth
ms.openlocfilehash: 6cac35e658343f606c1953f265c752335c70d81f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87667697"
---
# <a name="using-catalog-functions"></a><span data-ttu-id="1b0c0-102">Использование функций каталога</span><span class="sxs-lookup"><span data-stu-id="1b0c0-102">Using Catalog Functions</span></span>
  <span data-ttu-id="1b0c0-103">Все базы данных имеют структуру, содержащую данные, хранящиеся в базе данных.</span><span class="sxs-lookup"><span data-stu-id="1b0c0-103">All databases have a structure containing the data stored in the database.</span></span> <span data-ttu-id="1b0c0-104">Определение этой структуры вместе с другими сведениями, например разрешениями, хранится в каталоге (реализованном как набор системных таблиц), который называют словарем данных.</span><span class="sxs-lookup"><span data-stu-id="1b0c0-104">A definition of this structure, along with other information such as permissions, is stored in a catalog (implemented as a set of system tables), also known as a data dictionary.</span></span>  
  
 <span data-ttu-id="1b0c0-105">[!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)]Драйвер ODBC для собственного клиента позволяет приложению определить структуру базы данных с помощью вызовов функций каталога ODBC.</span><span class="sxs-lookup"><span data-stu-id="1b0c0-105">The [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client ODBC driver enables an application to determine the database structure through calls to ODBC catalog functions.</span></span> <span data-ttu-id="1b0c0-106">Функции каталога возвращают сведения в результирующих наборах и реализуются с помощью запросов хранимых процедур каталога к системным таблицам этого каталога.</span><span class="sxs-lookup"><span data-stu-id="1b0c0-106">Catalog functions return information in result sets and are implemented using catalog stored procedures to query the system tables in the catalog.</span></span> <span data-ttu-id="1b0c0-107">Например, приложение может запросить результирующий набор, содержащий сведения о всех таблицах в системе или всех столбцах в определенной таблице.</span><span class="sxs-lookup"><span data-stu-id="1b0c0-107">For example, an application might request a result set containing information about all the tables on the system or all the columns in a particular table.</span></span> <span data-ttu-id="1b0c0-108">Стандартные функции каталога ODBC используются для получения сведений о каталоге из [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)], к которому подключено приложение.</span><span class="sxs-lookup"><span data-stu-id="1b0c0-108">The standard ODBC catalog functions are used to get catalog information from the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] to which the application connected.</span></span>  
  
 [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] <span data-ttu-id="1b0c0-109">поддерживает распределенные запросы, в которых доступ к нескольким разнородным источникам данных OLE DB осуществляется одним запросом.</span><span class="sxs-lookup"><span data-stu-id="1b0c0-109">supports distributed queries in which data from multiple, heterogeneous OLE DB data sources is accessed in a single query.</span></span> <span data-ttu-id="1b0c0-110">Одним из методов доступа к удаленному источнику данных OLE DB является определение источника данных как связанного сервера.</span><span class="sxs-lookup"><span data-stu-id="1b0c0-110">One of the methods of accessing a remote OLE DB data source is to define the data source as a linked server.</span></span> <span data-ttu-id="1b0c0-111">Это можно сделать с помощью [sp_addlinkedserver](/sql/relational-databases/system-stored-procedures/sp-addlinkedserver-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="1b0c0-111">This can be done by using [sp_addlinkedserver](/sql/relational-databases/system-stored-procedures/sp-addlinkedserver-transact-sql).</span></span> <span data-ttu-id="1b0c0-112">После определения связанного сервера на объекты этого сервера могут ссылаться инструкции Transact-SQL, используя четырехкомпонентное имя:</span><span class="sxs-lookup"><span data-stu-id="1b0c0-112">After the linked server has been defined, objects in that server can be referenced in Transact-SQL statements by using a four-part name:</span></span>  
  
 <span data-ttu-id="1b0c0-113">*linked_server_name. catalog. Schema. object_name*.</span><span class="sxs-lookup"><span data-stu-id="1b0c0-113">*linked_server_name.catalog.schema.object_name*.</span></span>  
  
 <span data-ttu-id="1b0c0-114">Драйвер ODBC для собственного клиента [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] поддерживает две зависящие от драйвера функции, помогающие получить сведения о каталоге от связанных серверов.</span><span class="sxs-lookup"><span data-stu-id="1b0c0-114">The [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client ODBC driver supports two driver-specific functions that help get catalog information from linked servers:</span></span>  
  
-   <span data-ttu-id="1b0c0-115">**SQLLinkedServers**</span><span class="sxs-lookup"><span data-stu-id="1b0c0-115">**SQLLinkedServers**</span></span>  
  
     <span data-ttu-id="1b0c0-116">Возвращает список связанных серверов, определенных на локальном сервере.</span><span class="sxs-lookup"><span data-stu-id="1b0c0-116">Returns a list of the linked servers defined to the local server.</span></span>  
  
-   <span data-ttu-id="1b0c0-117">**SQLLinkedCatalogs**</span><span class="sxs-lookup"><span data-stu-id="1b0c0-117">**SQLLinkedCatalogs**</span></span>  
  
     <span data-ttu-id="1b0c0-118">Возвращает список каталогов, содержащихся на связанном сервере.</span><span class="sxs-lookup"><span data-stu-id="1b0c0-118">Returns a list of the catalogs contained in a linked server.</span></span>  
  
 <span data-ttu-id="1b0c0-119">После создания имени связанного сервера и каталога [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] драйвер ODBC для собственного клиента поддерживает получение сведений из каталога, используя имя из двух частей _linked_server_name_**.** _Каталог_ для *CatalogName* для следующих функций каталога ODBC:</span><span class="sxs-lookup"><span data-stu-id="1b0c0-119">After you have a linked server name and a catalog name, the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client ODBC driver supports getting information from the catalog by using a two-part name of _linked_server_name_**.**_catalog_ for *CatalogName* on the following ODBC catalog functions:</span></span>  
  
-   <span data-ttu-id="1b0c0-120">**SQLColumnPrivileges**</span><span class="sxs-lookup"><span data-stu-id="1b0c0-120">**SQLColumnPrivileges**</span></span>  
  
-   <span data-ttu-id="1b0c0-121">**SQLColumns**</span><span class="sxs-lookup"><span data-stu-id="1b0c0-121">**SQLColumns**</span></span>  
  
-   <span data-ttu-id="1b0c0-122">**SQLPrimaryKeys**</span><span class="sxs-lookup"><span data-stu-id="1b0c0-122">**SQLPrimaryKeys**</span></span>  
  
-   <span data-ttu-id="1b0c0-123">**SQLStatistics**</span><span class="sxs-lookup"><span data-stu-id="1b0c0-123">**SQLStatistics**</span></span>  
  
-   <span data-ttu-id="1b0c0-124">**SQLTablePrivileges**</span><span class="sxs-lookup"><span data-stu-id="1b0c0-124">**SQLTablePrivileges**</span></span>  
  
-   <span data-ttu-id="1b0c0-125">**SQLTables**</span><span class="sxs-lookup"><span data-stu-id="1b0c0-125">**SQLTables**</span></span>  
  
 <span data-ttu-id="1b0c0-126">Linked_server_name из двух частей _linked_server_name_**.** _Каталог_ также поддерживается для *фккаталогнаме* и *пккаталогнаме* на [SQLForeignKeys](../../native-client-odbc-api/sqlforeignkeys.md).</span><span class="sxs-lookup"><span data-stu-id="1b0c0-126">The two-part _linked_server_name_**.**_catalog_ is also supported for *FKCatalogName* and *PKCatalogName* on [SQLForeignKeys](../../native-client-odbc-api/sqlforeignkeys.md).</span></span>  
  
 <span data-ttu-id="1b0c0-127">Использование SQLLinkedServers и SQLLinkedCatalogs требует следующих файлов.</span><span class="sxs-lookup"><span data-stu-id="1b0c0-127">Using SQLLinkedServers and SQLLinkedCatalogs requires the following files:</span></span>  
  
-   <span data-ttu-id="1b0c0-128">sqlncli.h</span><span class="sxs-lookup"><span data-stu-id="1b0c0-128">sqlncli.h</span></span>  
  
     <span data-ttu-id="1b0c0-129">Включает прототипы функций и определения констант для функций каталога связанного сервера.</span><span class="sxs-lookup"><span data-stu-id="1b0c0-129">Includes function prototypes and constant definitions for the linked server catalog functions.</span></span> <span data-ttu-id="1b0c0-130">Файл sqlncli.h необходимо включить в приложение ODBC; при компиляции приложения он должен находиться в пути поиска включаемых файлов.</span><span class="sxs-lookup"><span data-stu-id="1b0c0-130">sqlncli.h must be included in the ODBC application and must be in the include path when the application is compiled.</span></span>  
  
-   <span data-ttu-id="1b0c0-131">sqlncli11.lib</span><span class="sxs-lookup"><span data-stu-id="1b0c0-131">sqlncli11.lib</span></span>  
  
     <span data-ttu-id="1b0c0-132">Должна находиться в пути к библиотекам компоновщика и определена как файл для связывания.</span><span class="sxs-lookup"><span data-stu-id="1b0c0-132">Must be in the library path of the linker and specified as a file to be linked.</span></span> <span data-ttu-id="1b0c0-133">Файл sqlncli11.lib поставляется вместе с драйвером ODBC [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client.</span><span class="sxs-lookup"><span data-stu-id="1b0c0-133">sqlncli11.lib is distributed with the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client ODBC driver.</span></span>  
  
-   <span data-ttu-id="1b0c0-134">sqlncli11.dll</span><span class="sxs-lookup"><span data-stu-id="1b0c0-134">sqlncli11.dll</span></span>  
  
     <span data-ttu-id="1b0c0-135">Необходима во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="1b0c0-135">Must be present at execution time.</span></span> <span data-ttu-id="1b0c0-136">Файл sqlncli11.dll поставляется вместе с драйвером ODBC [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client.</span><span class="sxs-lookup"><span data-stu-id="1b0c0-136">sqlncli11.dll is distributed with the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client ODBC driver.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1b0c0-137">См. также:</span><span class="sxs-lookup"><span data-stu-id="1b0c0-137">See Also</span></span>  
 <span data-ttu-id="1b0c0-138">[SQL Server Native Client &#40;ODBC&#41;](sql-server-native-client-odbc.md) </span><span class="sxs-lookup"><span data-stu-id="1b0c0-138">[SQL Server Native Client &#40;ODBC&#41;](sql-server-native-client-odbc.md) </span></span>  
 <span data-ttu-id="1b0c0-139">[SQLColumnPrivileges](../../native-client-odbc-api/sqlcolumnprivileges.md) </span><span class="sxs-lookup"><span data-stu-id="1b0c0-139">[SQLColumnPrivileges](../../native-client-odbc-api/sqlcolumnprivileges.md) </span></span>  
 <span data-ttu-id="1b0c0-140">[SQLColumns](../../native-client-odbc-api/sqlcolumns.md) </span><span class="sxs-lookup"><span data-stu-id="1b0c0-140">[SQLColumns](../../native-client-odbc-api/sqlcolumns.md) </span></span>  
 <span data-ttu-id="1b0c0-141">[SQLPrimaryKeys](../../native-client-odbc-api/sqlprimarykeys.md) </span><span class="sxs-lookup"><span data-stu-id="1b0c0-141">[SQLPrimaryKeys](../../native-client-odbc-api/sqlprimarykeys.md) </span></span>  
 <span data-ttu-id="1b0c0-142">[SQLTablePrivileges](../../native-client-odbc-api/sqltableprivileges.md) </span><span class="sxs-lookup"><span data-stu-id="1b0c0-142">[SQLTablePrivileges](../../native-client-odbc-api/sqltableprivileges.md) </span></span>  
 <span data-ttu-id="1b0c0-143">[SQLTables](../../native-client-odbc-api/sqltables.md) </span><span class="sxs-lookup"><span data-stu-id="1b0c0-143">[SQLTables](../../native-client-odbc-api/sqltables.md) </span></span>  
 [<span data-ttu-id="1b0c0-144">SQLStatistics</span><span class="sxs-lookup"><span data-stu-id="1b0c0-144">SQLStatistics</span></span>](../../statistics/statistics.md)  
  
  
