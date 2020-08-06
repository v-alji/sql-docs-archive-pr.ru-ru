---
title: Таблицы и индексы | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- OLE DB, indexes
- OLE DB, tables
- ITableDefinition interface
- tables [OLE DB]
- IIndexDefinition interface
- SQL Server Native Client OLE DB provider, tables
- SQL Server Native Client OLE DB provider, indexes
- indexes [OLE DB]
ms.assetid: 4217c6d8-8cd2-43dc-b36f-3cfd8a58fabc
author: rothja
ms.author: jroth
ms.openlocfilehash: abc7c314e433eb9f107bd191738d951706f1b50d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87665299"
---
# <a name="tables-and-indexes"></a><span data-ttu-id="bc24e-102">Таблицы и индексы</span><span class="sxs-lookup"><span data-stu-id="bc24e-102">Tables and Indexes</span></span>
  <span data-ttu-id="bc24e-103">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]Поставщик OLE DB собственного клиента предоставляет интерфейсы **IIndexDefinition** и **ITableDefinition** , позволяя потребителям создавать, изменять и удалять [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] таблицы и индексы.</span><span class="sxs-lookup"><span data-stu-id="bc24e-103">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider exposes the **IIndexDefinition** and **ITableDefinition** interfaces, allowing consumers to create, alter, and drop [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] tables and indexes.</span></span> <span data-ttu-id="bc24e-104">Допустимые определения таблиц и индексов зависят от версии [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="bc24e-104">Valid table and index definitions depend on the version of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
 <span data-ttu-id="bc24e-105">Возможность создавать и удалять таблицы и индексы зависит от прав доступа [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] пользователя клиентского приложения.</span><span class="sxs-lookup"><span data-stu-id="bc24e-105">The ability to create or drop tables and indexes depends on the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] access rights of the consumer-application user.</span></span> <span data-ttu-id="bc24e-106">Удаление таблицы может быть еще более ограничено присутствием декларативного ограничения ссылочной целостности или другими факторами.</span><span class="sxs-lookup"><span data-stu-id="bc24e-106">Dropping a table can be further constrained by the presence of declarative referential integrity constraints or other factors.</span></span>  
  
 <span data-ttu-id="bc24e-107">Большинство приложений нацелены [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] на использование SQL-DMO вместо этих [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] интерфейсов поставщика собственного клиента OLE DB.</span><span class="sxs-lookup"><span data-stu-id="bc24e-107">Most applications targeting [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] use SQL-DMO instead of these [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider interfaces.</span></span> <span data-ttu-id="bc24e-108">SQL-DMO — коллекция объектов OLE-автоматизации, которые поддерживают все административные функции [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="bc24e-108">SQL-DMO is a collection of OLE Automation objects that support all the administrative functions of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="bc24e-109">Приложения, ориентированные на несколько поставщиков OLE DB, используют стандартные интерфейсы OLE DB, поддерживаемые различными поставщиками OLE DB.</span><span class="sxs-lookup"><span data-stu-id="bc24e-109">Applications targeting multiple OLE DB providers use these generic OLE DB interfaces that are supported by the various OLE DB providers.</span></span>  
  
 <span data-ttu-id="bc24e-110">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] определяет следующее свойство в специфическом для поставщика наборе свойств DBPROPSET_SQLSERVERCOLUMN.</span><span class="sxs-lookup"><span data-stu-id="bc24e-110">In the provider-specific property set DBPROPSET_SQLSERVERCOLUMN, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] defines the following property.</span></span>  
  
|<span data-ttu-id="bc24e-111">Идентификатор свойства</span><span class="sxs-lookup"><span data-stu-id="bc24e-111">Property ID</span></span>|<span data-ttu-id="bc24e-112">Описание</span><span class="sxs-lookup"><span data-stu-id="bc24e-112">Description</span></span>|  
|-----------------|-----------------|  
|<span data-ttu-id="bc24e-113">SSPROP_COL_COLLATIONNAME</span><span class="sxs-lookup"><span data-stu-id="bc24e-113">SSPROP_COL_COLLATIONNAME</span></span>|<span data-ttu-id="bc24e-114">Тип: VT_BSTR</span><span class="sxs-lookup"><span data-stu-id="bc24e-114">Type: VT_BSTR</span></span><br /><br /> <span data-ttu-id="bc24e-115">Чтение и запись.</span><span class="sxs-lookup"><span data-stu-id="bc24e-115">R/W: Write</span></span><br /><br /> <span data-ttu-id="bc24e-116">По умолчанию: NULL</span><span class="sxs-lookup"><span data-stu-id="bc24e-116">Default: Null</span></span><br /><br /> <span data-ttu-id="bc24e-117">Описание: это свойство используется только в интерфейсе **ITableDefinition**.</span><span class="sxs-lookup"><span data-stu-id="bc24e-117">Description: This property is used only in **ITableDefinition**.</span></span> <span data-ttu-id="bc24e-118">Строка, указанная в этом свойстве, используется при создании инструкции [CREATE TABLE](/sql/t-sql/statements/create-table-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="bc24e-118">The string specified in this property is used when creating a [CREATE TABLE](/sql/t-sql/statements/create-table-transact-sql)</span></span><br /><br /> <span data-ttu-id="bc24e-119">.</span><span class="sxs-lookup"><span data-stu-id="bc24e-119">statement.</span></span>|  
  
## <a name="in-this-section"></a><span data-ttu-id="bc24e-120">в этом разделе</span><span class="sxs-lookup"><span data-stu-id="bc24e-120">In This Section</span></span>  
  
-   [<span data-ttu-id="bc24e-121">Создание таблиц SQL Server</span><span class="sxs-lookup"><span data-stu-id="bc24e-121">Creating SQL Server Tables</span></span>](../../relational-databases/native-client-ole-db-tables-indexes/creating-sql-server-tables.md)  
  
-   [<span data-ttu-id="bc24e-122">Добавление столбца к таблице SQL Server</span><span class="sxs-lookup"><span data-stu-id="bc24e-122">Adding a Column to a SQL Server Table</span></span>](../../relational-databases/native-client-ole-db-tables-indexes/adding-a-column-to-a-sql-server-table.md)  
  
-   [<span data-ttu-id="bc24e-123">Удаление столбца из таблицы SQL Server</span><span class="sxs-lookup"><span data-stu-id="bc24e-123">Removing a Column from a SQL Server Table</span></span>](../../relational-databases/native-client-ole-db-tables-indexes/removing-a-column-from-a-sql-server-table.md)  
  
-   [<span data-ttu-id="bc24e-124">Удаление таблицы SQL Server</span><span class="sxs-lookup"><span data-stu-id="bc24e-124">Dropping a SQL Server Table</span></span>](../../relational-databases/native-client-ole-db-tables-indexes/dropping-a-sql-server-table.md)  
  
-   [<span data-ttu-id="bc24e-125">Создание индексов SQL Server</span><span class="sxs-lookup"><span data-stu-id="bc24e-125">Creating SQL Server Indexes</span></span>](../../relational-databases/indexes/indexes.md)  
  
-   [<span data-ttu-id="bc24e-126">Удаление индекса SQL Server</span><span class="sxs-lookup"><span data-stu-id="bc24e-126">Dropping a SQL Server Index</span></span>](../../relational-databases/native-client-ole-db-tables-indexes/dropping-a-sql-server-index.md)  
  
## <a name="see-also"></a><span data-ttu-id="bc24e-127">См. также:</span><span class="sxs-lookup"><span data-stu-id="bc24e-127">See Also</span></span>  
 <span data-ttu-id="bc24e-128">[SQL Server Native Client &#40;OLE DB&#41;](../../relational-databases/native-client/ole-db/sql-server-native-client-ole-db.md) </span><span class="sxs-lookup"><span data-stu-id="bc24e-128">[SQL Server Native Client &#40;OLE DB&#41;](../../relational-databases/native-client/ole-db/sql-server-native-client-ole-db.md) </span></span>  
 <span data-ttu-id="bc24e-129">[DROP TABLE (Transact-SQL)](/sql/t-sql/statements/drop-table-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="bc24e-129">[DROP TABLE &#40;Transact-SQL&#41;](/sql/t-sql/statements/drop-table-transact-sql) </span></span>  
 <span data-ttu-id="bc24e-130">[CREATE INDEX (Transact-SQL)](/sql/t-sql/statements/create-index-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="bc24e-130">[CREATE INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-index-transact-sql) </span></span>  
 [<span data-ttu-id="bc24e-131">DROP INDEX (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="bc24e-131">DROP INDEX &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/drop-index-transact-sql)  
  
  
