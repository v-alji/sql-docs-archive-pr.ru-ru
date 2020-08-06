---
title: Наборы строк схемы, измененные для возвращающих табличное значение параметров OLE DB | Документы Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- schema rowsets [OLE DB]
- table-valued parameters (OLE DB), schema rowsets changed for (OLE DB)
ms.assetid: 581e3ead-53db-44da-8718-f3fc4b5108f1
author: rothja
ms.author: jroth
ms.openlocfilehash: e09d5127f332c8b6cc948be3eeb74e600bb856f6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87739797"
---
# <a name="schema-rowsets-changed-for-ole-db-table-valued-parameters"></a><span data-ttu-id="627a1-102">Наборы строк схемы, измененные для возвращающих табличное значение параметров OLE DB</span><span class="sxs-lookup"><span data-stu-id="627a1-102">Schema Rowsets Changed for OLE DB Table-Valued Parameters</span></span>
  <span data-ttu-id="627a1-103">Далее приведены наборы строк схемы, измененные или добавленные для поддержки возвращающих табличные значения параметров.</span><span class="sxs-lookup"><span data-stu-id="627a1-103">The following are the schema rowsets that have been changed or added to support table-valued parameters.</span></span>  
  
|<span data-ttu-id="627a1-104">Набор строк схемы</span><span class="sxs-lookup"><span data-stu-id="627a1-104">Schema rowset</span></span>|<span data-ttu-id="627a1-105">Описание</span><span class="sxs-lookup"><span data-stu-id="627a1-105">Description</span></span>|  
|-------------------|-----------------|  
|<span data-ttu-id="627a1-106">DBSCHEMA_PROCEDURE_PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="627a1-106">DBSCHEMA_PROCEDURE_PARAMETERS</span></span>|<span data-ttu-id="627a1-107">В конец набора строк были добавлены два новых столбца с именами SS_TYPE_CATALOG_NAME и SS_TYPE_SCHEMANAME.</span><span class="sxs-lookup"><span data-stu-id="627a1-107">Two new columns were added at the end of the rowset named SS_TYPE_CATALOG_NAME and SS_TYPE_SCHEMANAME.</span></span> <span data-ttu-id="627a1-108">Эти столбцы можно повторно использовать для будущих типов.</span><span class="sxs-lookup"><span data-stu-id="627a1-108">These columns could be re-used for future types.</span></span> <span data-ttu-id="627a1-109">Столбцы TYPE_NAME и LOCAL_TYPE_NAME содержат имя возвращающего табличное значение параметра типа TABLE.</span><span class="sxs-lookup"><span data-stu-id="627a1-109">The TYPE_NAME and LOCAL_TYPE_NAME columns will contain the name of the table-valued parameter TABLE type.</span></span> <span data-ttu-id="627a1-110">Столбец DATA_TYPE для возвращающих табличные значения параметров принимает значение DBTYPE_TABLE = 143.</span><span class="sxs-lookup"><span data-stu-id="627a1-110">The DATA_TYPE column will have value DBTYPE_TABLE = 143 for table-valued parameters.</span></span>|  
|<span data-ttu-id="627a1-111">DBSCHEMA_TABLE_TYPES</span><span class="sxs-lookup"><span data-stu-id="627a1-111">DBSCHEMA_TABLE_TYPES</span></span>|<span data-ttu-id="627a1-112">Этот набор строк был добавлен для поддержки возвращающих табличное значение параметров.</span><span class="sxs-lookup"><span data-stu-id="627a1-112">This rowset was added to support table-valued parameters.</span></span> <span data-ttu-id="627a1-113">Он аналогичен набору строк DBSCHEMA_TABLES, за исключением того, что возвращает метаданные только для табличных типов, а не для таблиц, представлений или синонимов.</span><span class="sxs-lookup"><span data-stu-id="627a1-113">It is identical to DBSCHEMA_TABLES, except that it returns metadata only for table types, rather than for tables, views, or synonyms.</span></span> <span data-ttu-id="627a1-114">Столбец TABLE_TYPE принимает значение TABLE TYPE.</span><span class="sxs-lookup"><span data-stu-id="627a1-114">The TABLE_TYPE column will have the value 'TABLE TYPE'.</span></span>|  
|<span data-ttu-id="627a1-115">DBSCHEMA_TABLE_TYPE_PRIMARY_KEYS</span><span class="sxs-lookup"><span data-stu-id="627a1-115">DBSCHEMA_TABLE_TYPE_PRIMARY_KEYS</span></span>|<span data-ttu-id="627a1-116">Этот набор строк был добавлен для поддержки возвращающих табличное значение параметров.</span><span class="sxs-lookup"><span data-stu-id="627a1-116">This rowset was added to support table-valued parameters.</span></span> <span data-ttu-id="627a1-117">Он аналогичен набору строк DBSCHEMA_PRIMARY_KEYS, за исключением того, что возвращает метаданные первичных ключей только для табличных типов, а не для таблиц.</span><span class="sxs-lookup"><span data-stu-id="627a1-117">It is identical to DBSCHEMA_PRIMARY_KEYS, except that it returns primary keys metadata only for table types, rather than for tables.</span></span>|  
|<span data-ttu-id="627a1-118">DBSCHEMA_TABLE_TYPE_COLUMNS</span><span class="sxs-lookup"><span data-stu-id="627a1-118">DBSCHEMA_TABLE_TYPE_COLUMNS</span></span>|<span data-ttu-id="627a1-119">Этот набор строк был добавлен для поддержки возвращающих табличное значение параметров.</span><span class="sxs-lookup"><span data-stu-id="627a1-119">This rowset was added to support table-valued parameters.</span></span> <span data-ttu-id="627a1-120">Он аналогичен набору строк DBSCHEMA_COLUMNS, за исключением того, что возвращает метаданные столбцов только для табличных типов, а не для таблиц, представлений или синонимов.</span><span class="sxs-lookup"><span data-stu-id="627a1-120">It is identical to DBSCHEMA_COLUMNS, except that it returns column metadata only for table types, rather than for tables, views, or synonyms.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="627a1-121">См. также:</span><span class="sxs-lookup"><span data-stu-id="627a1-121">See Also</span></span>  
 <span data-ttu-id="627a1-122">[Возвращающие табличное значение параметры &#40;OLE DB&#41;](table-valued-parameters-ole-db.md) </span><span class="sxs-lookup"><span data-stu-id="627a1-122">[Table-Valued Parameters &#40;OLE DB&#41;](table-valued-parameters-ole-db.md) </span></span>  
 [<span data-ttu-id="627a1-123">Использование возвращающих табличные значения параметров &#40;OLE DB&#41;</span><span class="sxs-lookup"><span data-stu-id="627a1-123">Use Table-Valued Parameters &#40;OLE DB&#41;</span></span>](../native-client-ole-db-how-to/use-table-valued-parameters-ole-db.md)  
  
  
