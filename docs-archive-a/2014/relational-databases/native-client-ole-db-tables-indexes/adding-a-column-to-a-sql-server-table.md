---
title: Добавление столбца к таблице SQL Server | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- columns [OLE DB]
- AddColumn function
- SQL Server Native Client OLE DB provider, columns
- adding columns
ms.assetid: 22bae18a-bc9d-4617-8660-ed8b17a468d4
author: rothja
ms.author: jroth
ms.openlocfilehash: 97aa2656ccde662a34e1dd80fd662b22f601d4ec
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87739800"
---
# <a name="adding-a-column-to-a-sql-server-table"></a><span data-ttu-id="7047c-102">Добавление столбца к таблице SQL Server</span><span class="sxs-lookup"><span data-stu-id="7047c-102">Adding a Column to a SQL Server Table</span></span>
  <span data-ttu-id="7047c-103">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]Поставщик OLE DB Native Client предоставляет функцию **ITableDefinition:: addColumn** .</span><span class="sxs-lookup"><span data-stu-id="7047c-103">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider exposes the **ITableDefinition::AddColumn** function.</span></span> <span data-ttu-id="7047c-104">Это позволяет пользователю добавить столбец в таблицу [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="7047c-104">This allows consumers to add a column to a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] table.</span></span>  
  
 <span data-ttu-id="7047c-105">При добавлении столбца в [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] таблицу [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] потребитель поставщика OLE DB собственного клиента ограничивается следующим образом:</span><span class="sxs-lookup"><span data-stu-id="7047c-105">When you add a column to a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] table, the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider consumer is constrained as follows:</span></span>  
  
-   <span data-ttu-id="7047c-106">Если значение DBPROP_COL_AUTOINCREMENT равно VARIANT_TRUE, то значение DBPROP_COL_NULLABLE должно быть равно VARIANT_FALSE.</span><span class="sxs-lookup"><span data-stu-id="7047c-106">If DBPROP_COL_AUTOINCREMENT is VARIANT_TRUE, DBPROP_COL_NULLABLE must be VARIANT_FALSE.</span></span>  
  
-   <span data-ttu-id="7047c-107">Если столбец принадлежит к типу [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] **timestamp**, значение DBPROP_COL_NULLABLE должно быть равно VARIANT_FALSE.</span><span class="sxs-lookup"><span data-stu-id="7047c-107">If the column is defined by using the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] **timestamp** data type, DBPROP_COL_NULLABLE must be VARIANT_FALSE.</span></span>  
  
-   <span data-ttu-id="7047c-108">Для столбца любого другого типа DBPROP_COL_NULLABLE должно быть равно VARIANT_TRUE.</span><span class="sxs-lookup"><span data-stu-id="7047c-108">For any other column definition, DBPROP_COL_NULLABLE must be VARIANT_TRUE.</span></span>  
  
 <span data-ttu-id="7047c-109">Пользователь задает имя таблицы в виде символьной строки в Юникоде в элементе *pwszName* объединения *uName* в параметре *pTableID*.</span><span class="sxs-lookup"><span data-stu-id="7047c-109">Consumers specify the table name as a Unicode character string in the *pwszName* member of the *uName* union in the *pTableID* parameter.</span></span> <span data-ttu-id="7047c-110">Элемент *eKind* параметра *pTableID* должен быть равен DBKIND_NAME.</span><span class="sxs-lookup"><span data-stu-id="7047c-110">The *eKind* member of *pTableID* must be DBKIND_NAME.</span></span>  
  
 <span data-ttu-id="7047c-111">Имя столбца задается в виде символьной строки в Юникоде в элементе *pwszName* объединения *uName* в элементе *dbcid* параметра *pColumnDesc* типа DBCOLUMNDESC.</span><span class="sxs-lookup"><span data-stu-id="7047c-111">The new column name is specified as a Unicode character string in the *pwszName* member of the *uName* union in the *dbcid* member of the DBCOLUMNDESC parameter *pColumnDesc*.</span></span> <span data-ttu-id="7047c-112">Элемент *eKind* должен быть равен DBKIND_NAME.</span><span class="sxs-lookup"><span data-stu-id="7047c-112">The *eKind* member must be DBKIND_NAME.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7047c-113">См. также:</span><span class="sxs-lookup"><span data-stu-id="7047c-113">See Also</span></span>  
 <span data-ttu-id="7047c-114">[Таблицы и индексы](tables-and-indexes.md) </span><span class="sxs-lookup"><span data-stu-id="7047c-114">[Tables and Indexes](tables-and-indexes.md) </span></span>  
 [<span data-ttu-id="7047c-115">ALTER TABLE (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="7047c-115">ALTER TABLE &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/alter-table-transact-sql)  
  
  
