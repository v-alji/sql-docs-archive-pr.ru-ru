---
title: Поддержка распределенных запросов в наборах строк схемы | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- DBPROPSET_SQLSERVERSESSION property
- schema rowsets [OLE DB]
- distributed queries [SQL Server], SQL Server Native Client OLE DB provider
- OLE DB, schema rowsets
- OLE DB rowsets, schema
- rowsets [OLE DB], schema
ms.assetid: 11354bb6-be42-4d8d-854c-42dd3dc38656
author: rothja
ms.author: jroth
ms.openlocfilehash: 48b57bbf40590f8ad5c049268f25fe66d2f94357
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87656366"
---
# <a name="distributed-query-support-in-schema-rowsets"></a><span data-ttu-id="f5aef-102">Поддержка распределенных запросов в наборах строк схемы</span><span class="sxs-lookup"><span data-stu-id="f5aef-102">Distributed Query Support in Schema Rowsets</span></span>
  <span data-ttu-id="f5aef-103">Для поддержки [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] распределенных запросов [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] интерфейс **IDBSchemaRowset** поставщика собственного OLE DB клиента возвращает метаданные на связанных серверах.</span><span class="sxs-lookup"><span data-stu-id="f5aef-103">To support [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] distributed queries, the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client OLE DB provider **IDBSchemaRowset** interface returns metadata on linked servers.</span></span>  
  
 <span data-ttu-id="f5aef-104">Если свойство SSPROP_QUOTEDCATALOGNAMES набора свойств DBPROPSET_SQLSERVERSESSION имеет значение VARIANT_TRUE, можно указать заключенный в кавычки идентификатор имени каталога (например, "my.catalog").</span><span class="sxs-lookup"><span data-stu-id="f5aef-104">If the DBPROPSET_SQLSERVERSESSION property SSPROP_QUOTEDCATALOGNAMES is VARIANT_TRUE, a quoted identifier can be specified for the catalog name (for example "my.catalog").</span></span> <span data-ttu-id="f5aef-105">При сужении вывода набора строк схемы по каталогу [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] поставщик OLE DB собственного клиента распознает имя, состоящий из двух частей, содержащего имя связанного сервера и каталога.</span><span class="sxs-lookup"><span data-stu-id="f5aef-105">When restricting schema rowset output by catalog, the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client OLE DB provider recognizes a two-part name containing the linked server and catalog name.</span></span> <span data-ttu-id="f5aef-106">Для наборов строк схемы, приведенных в таблице ниже, укажите имя каталога из двух частей как _linked_server_**.** _Каталог_ разрешает вывод в соответствующий каталог именованного связанного сервера.</span><span class="sxs-lookup"><span data-stu-id="f5aef-106">For the schema rowsets in the table below, specifying a two-part catalog name as _linked_server_**.**_catalog_ restricts output to the applicable catalog of the named linked server.</span></span>  
  
|<span data-ttu-id="f5aef-107">Набор строк схемы</span><span class="sxs-lookup"><span data-stu-id="f5aef-107">Schema rowset</span></span>|<span data-ttu-id="f5aef-108">Ограничение каталога</span><span class="sxs-lookup"><span data-stu-id="f5aef-108">Catalog restriction</span></span>|  
|-------------------|-------------------------|  
|<span data-ttu-id="f5aef-109">DBSCHEMA_CATALOGS</span><span class="sxs-lookup"><span data-stu-id="f5aef-109">DBSCHEMA_CATALOGS</span></span>|<span data-ttu-id="f5aef-110">CATALOG_NAME</span><span class="sxs-lookup"><span data-stu-id="f5aef-110">CATALOG_NAME</span></span>|  
|<span data-ttu-id="f5aef-111">DBSCHEMA_COLUMNS</span><span class="sxs-lookup"><span data-stu-id="f5aef-111">DBSCHEMA_COLUMNS</span></span>|<span data-ttu-id="f5aef-112">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="f5aef-112">TABLE_CATALOG</span></span>|  
|<span data-ttu-id="f5aef-113">DBSCHEMA_PRIMARY_KEYS</span><span class="sxs-lookup"><span data-stu-id="f5aef-113">DBSCHEMA_PRIMARY_KEYS</span></span>|<span data-ttu-id="f5aef-114">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="f5aef-114">TABLE_CATALOG</span></span>|  
|<span data-ttu-id="f5aef-115">DBSCHEMA_TABLES</span><span class="sxs-lookup"><span data-stu-id="f5aef-115">DBSCHEMA_TABLES</span></span>|<span data-ttu-id="f5aef-116">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="f5aef-116">TABLE_CATALOG</span></span>|  
|<span data-ttu-id="f5aef-117">DBSCHEMA_FOREIGN_KEYS</span><span class="sxs-lookup"><span data-stu-id="f5aef-117">DBSCHEMA_FOREIGN_KEYS</span></span>|<span data-ttu-id="f5aef-118">PK_TABLE_CATALOG FK_TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="f5aef-118">PK_TABLE_CATALOG FK_TABLE_CATALOG</span></span>|  
|<span data-ttu-id="f5aef-119">DBSCHEMA_INDEXES</span><span class="sxs-lookup"><span data-stu-id="f5aef-119">DBSCHEMA_INDEXES</span></span>|<span data-ttu-id="f5aef-120">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="f5aef-120">TABLE_CATALOG</span></span>|  
|<span data-ttu-id="f5aef-121">DBSCHEMA_COLUMN_PRIVILEGES</span><span class="sxs-lookup"><span data-stu-id="f5aef-121">DBSCHEMA_COLUMN_PRIVILEGES</span></span>|<span data-ttu-id="f5aef-122">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="f5aef-122">TABLE_CATALOG</span></span>|  
|<span data-ttu-id="f5aef-123">DBSCHEMA_TABLE_PRIVILEGES</span><span class="sxs-lookup"><span data-stu-id="f5aef-123">DBSCHEMA_TABLE_PRIVILEGES</span></span>|<span data-ttu-id="f5aef-124">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="f5aef-124">TABLE_CATALOG</span></span>|  
  
> [!NOTE]  
>  <span data-ttu-id="f5aef-125">Чтобы ограничить набор строк схемы всеми каталогами со связанного сервера, используйте синтаксис *связанный_сервер* (где точка-разделитель является частью спецификации имени).</span><span class="sxs-lookup"><span data-stu-id="f5aef-125">To restrict a schema rowset to all catalogs from a linked server, use the syntax *linked_server* (where the period separator is part of the name specification).</span></span> <span data-ttu-id="f5aef-126">Этот синтаксис эквивалентен указанию значения NULL для ограничения имени каталога; он также используется, когда связанный сервер указывает на источник данных, который не поддерживает каталоги.</span><span class="sxs-lookup"><span data-stu-id="f5aef-126">This syntax is equivalent to specifying NULL for the catalog name restriction and is also used when the linked server indicates a data source that does not support catalogs.</span></span>  
  
 <span data-ttu-id="f5aef-127">[!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)]Поставщик OLE DB собственного клиента определяет набор строк схемы LINKEDSERVERS, возвращая список OLE DB источников данных, зарегистрированных как связанные серверы.</span><span class="sxs-lookup"><span data-stu-id="f5aef-127">The [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client OLE DB provider defines the schema rowset LINKEDSERVERS, returning a list of OLE DB data sources registered as linked servers.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f5aef-128">См. также:</span><span class="sxs-lookup"><span data-stu-id="f5aef-128">See Also</span></span>  
 <span data-ttu-id="f5aef-129">[&#40;OLE DB поддерживает набор строк схемы&#41;](schema-rowset-support-ole-db.md) </span><span class="sxs-lookup"><span data-stu-id="f5aef-129">[Schema Rowset Support &#40;OLE DB&#41;](schema-rowset-support-ole-db.md) </span></span>  
 [<span data-ttu-id="f5aef-130">Набор строк LINKEDSERVERS (OLE DB)</span><span class="sxs-lookup"><span data-stu-id="f5aef-130">LINKEDSERVERS Rowset &#40;OLE DB&#41;</span></span>](schema-rowsets-linkedservers-rowset.md)  
  
  
