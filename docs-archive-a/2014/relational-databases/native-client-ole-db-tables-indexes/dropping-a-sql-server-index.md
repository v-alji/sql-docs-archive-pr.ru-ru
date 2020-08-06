---
title: Удаление индекса SQL Server | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- removing indexes
- deleting indexes
- DropIndex function
- dropping indexes
- SQL Server Native Client OLE DB provider, indexes
- indexes [OLE DB]
ms.assetid: add3ba14-10b1-4723-b7c0-3e83689e9fdd
author: rothja
ms.author: jroth
ms.openlocfilehash: 1267cc92645ff8b28757ad2d266e58917fcb4b28
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87665303"
---
# <a name="dropping-a-sql-server-index"></a><span data-ttu-id="2cc67-102">Удаление индекса SQL Server</span><span class="sxs-lookup"><span data-stu-id="2cc67-102">Dropping a SQL Server Index</span></span>
  <span data-ttu-id="2cc67-103">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]Поставщик OLE DBа собственного клиента предоставляет функцию **IIndexDefinition::D ропиндекс** .</span><span class="sxs-lookup"><span data-stu-id="2cc67-103">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider exposes the **IIndexDefinition::DropIndex** function.</span></span> <span data-ttu-id="2cc67-104">Это позволяет потребителям удалять индексы из таблицы [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="2cc67-104">This allows consumers to remove an index from a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] table.</span></span>  
  
 <span data-ttu-id="2cc67-105">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]Поставщик OLE DB собственного клиента предоставляет некоторые [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] ограничения первичного ключа и уникальности в качестве индексов.</span><span class="sxs-lookup"><span data-stu-id="2cc67-105">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider exposes some [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] PRIMARY KEY and UNIQUE constraints as indexes.</span></span> <span data-ttu-id="2cc67-106">Владелец таблицы, владелец базы данных и члены некоторых административных ролей могут изменять таблицу [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], удаляя ограничения.</span><span class="sxs-lookup"><span data-stu-id="2cc67-106">The table owner, database owner, and some administrative role members can modify a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] table, dropping a constraint.</span></span> <span data-ttu-id="2cc67-107">По умолчанию только владелец таблицы может удалять существующие индексы.</span><span class="sxs-lookup"><span data-stu-id="2cc67-107">By default, only the table owner can drop an existing index.</span></span> <span data-ttu-id="2cc67-108">Таким образом, будет ли функция **DropIndex** выполнена успешно или с ошибкой, зависит не только от прав доступа пользователя приложения, но также и от указанного типа индекса.</span><span class="sxs-lookup"><span data-stu-id="2cc67-108">Therefore, **DropIndex** success or failure depends not only on the application user's access rights but also on the type of index indicated.</span></span>  
  
 <span data-ttu-id="2cc67-109">Пользователь задает имя таблицы в виде символьной строки в Юникоде в элементе *pwszName* объединения *uName* в параметре *pTableID*.</span><span class="sxs-lookup"><span data-stu-id="2cc67-109">Consumers specify the table name as a Unicode character string in the *pwszName* member of the *uName* union in the *pTableID* parameter.</span></span> <span data-ttu-id="2cc67-110">Элемент *eKind* параметра *pTableID* должен быть равен DBKIND_NAME.</span><span class="sxs-lookup"><span data-stu-id="2cc67-110">The *eKind* member of *pTableID* must be DBKIND_NAME.</span></span>  
  
 <span data-ttu-id="2cc67-111">Потребитель задает имя индекса в виде строки в Юникоде в элементе *pwszName* объединения *uName* в параметре *pIndexID*.</span><span class="sxs-lookup"><span data-stu-id="2cc67-111">Consumers specify the index name as a Unicode character string in the *pwszName* member of the *uName* union in the *pIndexID* parameter.</span></span> <span data-ttu-id="2cc67-112">Элемент *eKind* параметра *pIndexID* должен быть равен DBKIND_NAME.</span><span class="sxs-lookup"><span data-stu-id="2cc67-112">The *eKind* member of *pIndexID* must be DBKIND_NAME.</span></span> <span data-ttu-id="2cc67-113">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]Поставщик OLE DB собственного клиента не поддерживает функцию OLE DB удаления всех индексов в таблице, если *pIndexID* имеет значение null.</span><span class="sxs-lookup"><span data-stu-id="2cc67-113">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider does not support the OLE DB feature of dropping all indexes on a table when *pIndexID* is null.</span></span> <span data-ttu-id="2cc67-114">Если значение параметра *pIndexID* равно NULL, то возвращается E_INVALIDARG.</span><span class="sxs-lookup"><span data-stu-id="2cc67-114">If *pIndexID* is null, E_INVALIDARG is returned.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2cc67-115">См. также:</span><span class="sxs-lookup"><span data-stu-id="2cc67-115">See Also</span></span>  
 <span data-ttu-id="2cc67-116">[Таблицы и индексы](tables-and-indexes.md) </span><span class="sxs-lookup"><span data-stu-id="2cc67-116">[Tables and Indexes](tables-and-indexes.md) </span></span>  
 <span data-ttu-id="2cc67-117">[ALTER TABLE (Transact-SQL)](/sql/t-sql/statements/alter-table-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="2cc67-117">[ALTER TABLE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-table-transact-sql) </span></span>  
 [<span data-ttu-id="2cc67-118">DROP INDEX (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="2cc67-118">DROP INDEX &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/drop-index-transact-sql)  
  
  
