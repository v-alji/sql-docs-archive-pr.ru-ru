---
title: Поддержка типов параметров OLE DB, возвращающих табличные значения | Документы Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- table-valued parameters (OLE DB), API support (OLE DB)
ms.assetid: 147036a0-260e-4f81-8b3b-89209e023a32
author: rothja
ms.author: jroth
ms.openlocfilehash: 48d5fd780b2eaa2fc18e39071d3b10fde897b82c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87657737"
---
# <a name="ole-db-table-valued-parameter-type-support"></a><span data-ttu-id="004ca-102">Поддержка типа возвращающего табличное значение параметра OLE DB</span><span class="sxs-lookup"><span data-stu-id="004ca-102">OLE DB Table-Valued Parameter Type Support</span></span>
  <span data-ttu-id="004ca-103">Этот раздел содержит описание поддержки типа параметра OLE DB для параметров, возвращающих табличное значение.</span><span class="sxs-lookup"><span data-stu-id="004ca-103">This topic describes OLE DB type support for table-value parameters.</span></span>  
  
## <a name="table-valued-parameter-rowset-object"></a><span data-ttu-id="004ca-104">Объект набора строк параметра, возвращающего табличное значение</span><span class="sxs-lookup"><span data-stu-id="004ca-104">Table-Valued Parameter Rowset Object</span></span>  
 <span data-ttu-id="004ca-105">Можно создать специальный объект набора строк для параметров, возвращающих табличное значение.</span><span class="sxs-lookup"><span data-stu-id="004ca-105">You can create a specialized rowset object for table-valued parameters.</span></span> <span data-ttu-id="004ca-106">Чтобы создать объект набора строк для параметра, возвращающего табличное значение, можно применить ITableDefinitionWithConstraints::CreateTableWithConstraints или IOpenRowset::OpenRowset.</span><span class="sxs-lookup"><span data-stu-id="004ca-106">You create the table-valued parameter rowset object by using ITableDefinitionWithConstraints::CreateTableWithConstraints or IOpenRowset::OpenRowset.</span></span> <span data-ttu-id="004ca-107">Для этого установите элемент *eKind* параметра *pTableID* в значение DBKIND_GUID_NAME и укажите CLSID_ROWSET_INMEMORY как элемент *guid*.</span><span class="sxs-lookup"><span data-stu-id="004ca-107">To do this, set the *eKind* member of the *pTableID* parameter to DBKIND_GUID_NAME, and provide the CLSID_ROWSET_INMEMORY as the *guid* member.</span></span> <span data-ttu-id="004ca-108">Имя типа сервера для параметра, возвращающего табличное значение, необходимо указать в элементе *pwszName* параметра *pTableID* при вызове IOpenRowset::OpenRowset.</span><span class="sxs-lookup"><span data-stu-id="004ca-108">The server type name for the table-valued parameter must be specified in the *pwszName* member of *pTableID* when using IOpenRowset::OpenRowset.</span></span> <span data-ttu-id="004ca-109">Объект набора строк параметра, возвращающего табличное значение, действует так же, как объект поставщика OLE DB собственного клиента для SQL Server.</span><span class="sxs-lookup"><span data-stu-id="004ca-109">The table-valued parameter rowset object behaves like a regular SQL Server Native Client OLE DB Provider object.</span></span>  
  
```  
const GUID CLSID_ROWSET_TVP =   
{0xc7ef28d5, 0x7bee, 0x443f, {0x86, 0xda, 0xe3, 0x98, 0x4f, 0xcd, 0x4d, 0xf9}};  
  
CoType RowsetTVP  
{  
[mandatory] interface IAccessor;  
[mandatory] interface IColumnsInfo;  
[mandatory] interface IConvertType;  
[mandatory] interface IRowset;  
[mandatory] interface IRowsetInfo;  
[optional]  interface IColumnsRowset;  
[optional]  interface IRowsetChange;  
[optional]  interface ISupportErrorInfo;  
};  
```  
  
## <a name="dbtype_table"></a><span data-ttu-id="004ca-110">DBTYPE_TABLE</span><span class="sxs-lookup"><span data-stu-id="004ca-110">DBTYPE_TABLE</span></span>  
 <span data-ttu-id="004ca-111">Новый тип, DBTYPE_TABLE, представляет собой табличный тип.</span><span class="sxs-lookup"><span data-stu-id="004ca-111">A new type, DBTYPE_TABLE, represents a table type.</span></span> <span data-ttu-id="004ca-112">Этот тип описывает возвращающие табличное значение параметры в различных интерфейсах OLE DB, где требуется тип DBTYPE.</span><span class="sxs-lookup"><span data-stu-id="004ca-112">This type specifies table-valued parameters in various OLE DB interfaces where a DBTYPE is required.</span></span>  
  
```  
#define DBTYPE_TABLE (143)  
```  
  
 <span data-ttu-id="004ca-113">DBTYPE_TABLE имеет такой же формат, что и DBTYPE_IUNKNOWN.</span><span class="sxs-lookup"><span data-stu-id="004ca-113">DBTYPE_TABLE has the same format as DBTYPE_IUNKNOWN.</span></span> <span data-ttu-id="004ca-114">Представляет собой указатель на объект в буфере данных.</span><span class="sxs-lookup"><span data-stu-id="004ca-114">It is a pointer to an object in the data buffer.</span></span> <span data-ttu-id="004ca-115">Чтобы определить полную спецификацию в привязках, потребитель заполняет буфер DBOBJECT, задавая для параметра *iid* один из интерфейсов объекта набора строк (IID_IRowset).</span><span class="sxs-lookup"><span data-stu-id="004ca-115">For complete specification in the bindings, the consumer fills up the DBOBJECT buffer, with *iid* set to one of the rowset object interfaces (IID_IRowset).</span></span> <span data-ttu-id="004ca-116">Если объект DBOBJECT в привязках не указан, то предполагается использование объекта IID_IRowset.</span><span class="sxs-lookup"><span data-stu-id="004ca-116">If no DBOBJECT is specified in the bindings, IID_IRowset will be assumed.</span></span>  
  
 <span data-ttu-id="004ca-117">Прямые и обратные преобразования в тип DBTYPE_TABLE для каких-либо других типов не поддерживаются.</span><span class="sxs-lookup"><span data-stu-id="004ca-117">Conversions to and from DBTYPE_TABLE for any other types are not supported.</span></span> <span data-ttu-id="004ca-118">Метод IConvertType::CanConvert возвращает значение S_FALSE для неподдерживаемого преобразования применительно к любому запросу, отличному от преобразования DBTYPE_TABLE в DBTYPE_TABLE.</span><span class="sxs-lookup"><span data-stu-id="004ca-118">IConvertType::CanConvert will return S_FALSE for unsupported conversion for any request other than DBTYPE_TABLE to DBTYPE_TABLE conversion.</span></span> <span data-ttu-id="004ca-119">При этом предполагается использование параметра DBCONVERTFLAGS_PARAMETER объекта Command.</span><span class="sxs-lookup"><span data-stu-id="004ca-119">This assumes DBCONVERTFLAGS_PARAMETER on the Command object.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="004ca-120">Методы</span><span class="sxs-lookup"><span data-stu-id="004ca-120">Methods</span></span>  
 <span data-ttu-id="004ca-121">Сведения о методах OLE DB, поддерживающих параметры, возвращающие табличное значение, см. в статье [Поддержка типа возвращающего табличное значение параметра OLE DB (методы)](ole-db-table-valued-parameter-type-support-methods.md).</span><span class="sxs-lookup"><span data-stu-id="004ca-121">For information about OLE DB methods that support table-valued parameters, see [OLE DB Table-Valued Parameter Type Support &#40;Methods&#41;](ole-db-table-valued-parameter-type-support-methods.md).</span></span>  
  
## <a name="properties"></a><span data-ttu-id="004ca-122">Свойства</span><span class="sxs-lookup"><span data-stu-id="004ca-122">Properties</span></span>  
 <span data-ttu-id="004ca-123">Сведения о свойствах OLE DB, поддерживающих параметры, возвращающие табличное значение, см. в статье [Поддержка типа возвращающего табличное значение параметра OLE DB (свойства)](ole-db-table-valued-parameter-type-support-properties.md).</span><span class="sxs-lookup"><span data-stu-id="004ca-123">For information about OLE DB properties that support table-valued parameters, see [OLE DB Table-Valued Parameter Type Support &#40;Properties&#41;](ole-db-table-valued-parameter-type-support-properties.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="004ca-124">См. также:</span><span class="sxs-lookup"><span data-stu-id="004ca-124">See Also</span></span>  
 <span data-ttu-id="004ca-125">[Возвращающие табличное значение параметры &#40;OLE DB&#41;](table-valued-parameters-ole-db.md) </span><span class="sxs-lookup"><span data-stu-id="004ca-125">[Table-Valued Parameters &#40;OLE DB&#41;](table-valued-parameters-ole-db.md) </span></span>  
 [<span data-ttu-id="004ca-126">Использование возвращающих табличные значения параметров &#40;OLE DB&#41;</span><span class="sxs-lookup"><span data-stu-id="004ca-126">Use Table-Valued Parameters &#40;OLE DB&#41;</span></span>](../native-client-ole-db-how-to/use-table-valued-parameters-ole-db.md)  
  
  
