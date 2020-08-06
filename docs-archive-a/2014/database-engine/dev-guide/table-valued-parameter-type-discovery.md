---
title: Обнаружение типа для возвращающего табличное значение параметра | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: reference
helpviewer_keywords:
- table-valued parameters, type discovery
ms.assetid: f55818c2-ebb5-4cf6-8c0c-0da41f592560
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: ab8d837e4ddf74256e4bae70f772557ec8ff67f7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87733014"
---
# <a name="table-valued-parameter-type-discovery"></a><span data-ttu-id="7080a-102">Обнаружение типа возвращающего табличное значение параметра</span><span class="sxs-lookup"><span data-stu-id="7080a-102">Table-Valued Parameter Type Discovery</span></span>
  <span data-ttu-id="7080a-103">Потребитель, то есть клиентское приложение, использующее [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] поставщик OLE DB собственного клиента, может определить тип каждого параметра команды, если текст команды был передан поставщику OLE DB.</span><span class="sxs-lookup"><span data-stu-id="7080a-103">The consumer-that is, the client application using the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB Provider-can discover the type of each command parameter if the command text has been given to the OLE DB Provider.</span></span> <span data-ttu-id="7080a-104">После того как тип возвращающего табличное значение параметра становится известен, потребитель может определить метаданные для каждого отдельного столбца возвращающего табличное значение параметра.</span><span class="sxs-lookup"><span data-stu-id="7080a-104">After the type of a table-valued parameter is known, the consumer can discover the metadata information for each individual column of the table-valued parameter.</span></span>  
  
 <span data-ttu-id="7080a-105">Сведения о типе параметров процедур предоставляются методом ICommandWithParameters::GetParameterInfo для большинства типов параметров.</span><span class="sxs-lookup"><span data-stu-id="7080a-105">The type information of procedure parameters is supported by ICommandWithParameters::GetParameterInfo for most parameter types.</span></span> <span data-ttu-id="7080a-106">Начиная с [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] , с появлением определяемых пользователем типов и `xml` типа данных метод GetParameterInfo недостаточно для этой цели, поскольку было невозможно предоставить сведения о определяемом пользователем типе (имя, схема и каталог) через ICommandWithParameters.</span><span class="sxs-lookup"><span data-stu-id="7080a-106">Beginning with [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)], with the introduction of user-defined types and the `xml` data type, the GetParameterInfo method was not sufficient for this purpose because it was not possible to provide user-defined type information (name, schema, and catalog) through ICommandWithParameters.</span></span> <span data-ttu-id="7080a-107">Для предоставления расширенных сведений о типе был определен новый интерфейс ISSCommandWithParameters.</span><span class="sxs-lookup"><span data-stu-id="7080a-107">A new interface, ISSCommandWithParameters, was defined to provide extended type information.</span></span>  
  
 <span data-ttu-id="7080a-108">Среди прочего, интерфейс ISSCommandWithParameters позволяет получать подробные сведения для возвращающих табличное значение параметров.</span><span class="sxs-lookup"><span data-stu-id="7080a-108">For table-valued parameters, you also use the ISSCommandWithParameters interface to discover detailed information.</span></span> <span data-ttu-id="7080a-109">Клиент вызывает ISSCommandWithParameters::GetParameterInfo после подготовки объекта команды.</span><span class="sxs-lookup"><span data-stu-id="7080a-109">The client calls ISSCommandWithParameters::GetParameterInfo after preparing the command object.</span></span> <span data-ttu-id="7080a-110">Для возвращающих табличные значения параметров элемент *wType* структуры DBPARAMINFO устанавливается поставщиком в значение DBTYPE_TABLE.</span><span class="sxs-lookup"><span data-stu-id="7080a-110">For table-valued parameters, the *wType* member of the DBPARAMINFO structure is set to DBTYPE_TABLE by the provider.</span></span> <span data-ttu-id="7080a-111">Поле *ulParamSize* структуры DBPARAMINFO имеет значение ~0.</span><span class="sxs-lookup"><span data-stu-id="7080a-111">The *ulParamSize* field of DBPARAMINFO structure has a value of ~0.</span></span>  
  
 <span data-ttu-id="7080a-112">Объект-получатель затем запрашивает дополнительные свойства (имя каталога для типа табличного параметра, имя схемы для типа табличного параметра, имя типа табличного параметра, порядок столбцов и столбцы по умолчанию) с помощью ISSCommandWithParameters::GetParameterProperties.</span><span class="sxs-lookup"><span data-stu-id="7080a-112">The consumer would then request additional properties (table-valued parameter type catalog name, table-valued parameter type schema name, table-valued parameter type name, column ordering, and default columns) by using ISSCommandWithParameters::GetParameterProperties.</span></span>  
  
 <span data-ttu-id="7080a-113">После того как имя типа стало известно, для получения сведений об отдельном столбце потребитель должен либо вызвать метод IOpenRowset::OpenRowset, либо получить набор строк DBSCHEMA_TABLE_TYPE_COLUMNS, указав имя типа возвращающего табличное значение параметра в качестве имени таблицы.</span><span class="sxs-lookup"><span data-stu-id="7080a-113">After the type name is known, to retrieve the individual column information the consumer must either call IOpenRowset::OpenRowsetor obtain the DBSCHEMA_TABLE_TYPE_COLUMNS rowset by specifying the table-valued parameter type name as the table name.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7080a-114">См. также:</span><span class="sxs-lookup"><span data-stu-id="7080a-114">See Also</span></span>  
 <span data-ttu-id="7080a-115">[Возвращающие табличное значение параметры &#40;OLE DB&#41;](../../relational-databases/native-client-ole-db-table-valued-parameters/table-valued-parameters-ole-db.md) </span><span class="sxs-lookup"><span data-stu-id="7080a-115">[Table-Valued Parameters &#40;OLE DB&#41;](../../relational-databases/native-client-ole-db-table-valued-parameters/table-valued-parameters-ole-db.md) </span></span>  
 [<span data-ttu-id="7080a-116">Использование возвращающих табличные значения параметров &#40;OLE DB&#41;</span><span class="sxs-lookup"><span data-stu-id="7080a-116">Use Table-Valued Parameters &#40;OLE DB&#41;</span></span>](../../relational-databases/native-client-ole-db-how-to/use-table-valued-parameters-ole-db.md)  
  
  
