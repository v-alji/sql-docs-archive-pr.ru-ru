---
title: Возвращающие табличное значение параметры (OLE DB) | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- OLE DB, table-valued parameters
- table-valued parameters (OLE DB)
ms.assetid: 4298b73d-615b-4d28-9843-03b4d5fc489e
author: rothja
ms.author: jroth
ms.openlocfilehash: 41d125bcb254125d7f7562ca1873e8af03dab929
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87738252"
---
# <a name="table-valued-parameters-ole-db"></a><span data-ttu-id="ef354-102">Возвращающие табличное значение параметры (OLE DB)</span><span class="sxs-lookup"><span data-stu-id="ef354-102">Table-Valued Parameters (OLE DB)</span></span>
  <span data-ttu-id="ef354-103">В этом разделе описывается поддержка возвращающих табличное значение параметров в поставщике OLE DB для собственного клиента [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ef354-103">This section describes support for table-valued parameters in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB Provider.</span></span> <span data-ttu-id="ef354-104">Дополнительные сведения см. в разделе [Параметры, возвращающие ](../native-client/features/table-valued-parameters-sql-server-native-client.md)табличное значение, &#40;SQL Server Native Client&#41;.</span><span class="sxs-lookup"><span data-stu-id="ef354-104">For additional overview information, see [Table-Valued Parameters &#40;SQL Server Native Client&#41;](../native-client/features/table-valued-parameters-sql-server-native-client.md).</span></span> <span data-ttu-id="ef354-105">Пример использования можно найти в статье [Использование возвращающих табличные значения параметров (OLE DB)](../native-client-ole-db-how-to/use-table-valued-parameters-ole-db.md).</span><span class="sxs-lookup"><span data-stu-id="ef354-105">For a sample, see [Use Table-Valued Parameters &#40;OLE DB&#41;](../native-client-ole-db-how-to/use-table-valued-parameters-ole-db.md).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ef354-106">Remarks</span><span class="sxs-lookup"><span data-stu-id="ef354-106">Remarks</span></span>  
 <span data-ttu-id="ef354-107">В настоящее время можно отправить многострочные данные на сервер как параметры для процедуры с наборами параметров (параметр DBPARAMS метода `ICommand::Execute`).</span><span class="sxs-lookup"><span data-stu-id="ef354-107">Currently, you can send multirow data to the server as parameters to a procedure with parameter sets (the DBPARAMS parameter in `ICommand::Execute`).</span></span> <span data-ttu-id="ef354-108">При использовании набора параметров каждый элемент набора должен быть отправлен на сервер в отдельном запросе удаленного вызова процедур (RPC).</span><span class="sxs-lookup"><span data-stu-id="ef354-108">With parameter sets, every element of the set has to be sent in a separate remote procedure call (RPC) request to the server.</span></span> <span data-ttu-id="ef354-109">Возвращающие табличное значение параметры обеспечивают похожую функциональность, но лучше интегрированы с сервером.</span><span class="sxs-lookup"><span data-stu-id="ef354-109">Table-valued parameters provide similar functionality, but there is better integration with the server.</span></span> <span data-ttu-id="ef354-110">При этом уменьшается число запросов RPC, а на сервере возможны операции, основанные на наборах.</span><span class="sxs-lookup"><span data-stu-id="ef354-110">This reduces the number of RPC requests and enables set-based operations on the server.</span></span>  
  
 <span data-ttu-id="ef354-111">Возвращающие табличное значение параметры поддерживаются в поставщике OLE DB для собственного клиента [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] как объекты OLE DB `Rowset`.</span><span class="sxs-lookup"><span data-stu-id="ef354-111">Table-value parameters are supported in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB Provider as OLE DB `Rowset` objects.</span></span> <span data-ttu-id="ef354-112">Любой объект `Rowset` может быть предоставлен потребителем (то есть клиентским приложением, которое использует поставщика OLE DB для собственного клиента [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]) в качестве заполнителя для возвращающих табличное значение параметров.</span><span class="sxs-lookup"><span data-stu-id="ef354-112">Any `Rowset` object could be provided by the consumer (that is, the client application using [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB Provider) as a placeholder for table-valued parameter parameters.</span></span> <span data-ttu-id="ef354-113">Возвращающие табличное значение параметры обрабатываются как параметры других типов [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ef354-113">Table-valued parameters are treated like other [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] parameter types.</span></span> <span data-ttu-id="ef354-114">Поставщик OLE DB для собственного клиента [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] обеспечивает интерфейсы создания, обнаружения, определения, привязки и схемы.</span><span class="sxs-lookup"><span data-stu-id="ef354-114">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB Provider provides creation, discovery, specification, binding and schema interfaces.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="ef354-115">в этом разделе</span><span class="sxs-lookup"><span data-stu-id="ef354-115">In This Section</span></span>  
  
-   [<span data-ttu-id="ef354-116">Создание набора строк возвращающего табличное значение параметра</span><span class="sxs-lookup"><span data-stu-id="ef354-116">Table-Valued Parameter Rowset Creation</span></span>](table-valued-parameter-rowset-creation.md)  
  
-   [<span data-ttu-id="ef354-117">Обнаружение типа возвращающего табличное значение параметра</span><span class="sxs-lookup"><span data-stu-id="ef354-117">Table-Valued Parameter Type Discovery</span></span>](../../database-engine/dev-guide/table-valued-parameter-type-discovery.md)  
  
-   [<span data-ttu-id="ef354-118">Выполнение команд, содержащих возвращающие табличные значения параметры</span><span class="sxs-lookup"><span data-stu-id="ef354-118">Executing Commands Containing Table-Valued Parameters</span></span>](executing-commands-containing-table-valued-parameters.md)  
  
-   [<span data-ttu-id="ef354-119">Вставка данных в параметры, возвращающие табличные значения</span><span class="sxs-lookup"><span data-stu-id="ef354-119">Inserting Data into Table-Valued Parameters</span></span>](inserting-data-into-table-valued-parameters.md)  
  
-   [<span data-ttu-id="ef354-120">Наборы строк схемы, измененные для возвращающих табличное значение параметров OLE DB</span><span class="sxs-lookup"><span data-stu-id="ef354-120">Schema Rowsets Changed for OLE DB Table-Valued Parameters</span></span>](schema-rowsets-changed-for-ole-db-table-valued-parameters.md)  
  
-   [<span data-ttu-id="ef354-121">Поддержка типов параметров OLE DB, возвращающих табличные значения</span><span class="sxs-lookup"><span data-stu-id="ef354-121">OLE DB Table-Valued Parameter Type Support</span></span>](ole-db-table-valued-parameter-type-support.md)  
  
-   [<span data-ttu-id="ef354-122">Поддержка типов параметров OLE DB, возвращающих табличные значения &#40;методы&#41;</span><span class="sxs-lookup"><span data-stu-id="ef354-122">OLE DB Table-Valued Parameter Type Support &#40;Methods&#41;</span></span>](ole-db-table-valued-parameter-type-support-methods.md)  
  
-   [<span data-ttu-id="ef354-123">Поддержка типов параметров OLE DB, возвращающих табличные значения &#40;свойства&#41;</span><span class="sxs-lookup"><span data-stu-id="ef354-123">OLE DB Table-Valued Parameter Type Support &#40;Properties&#41;</span></span>](ole-db-table-valued-parameter-type-support-properties.md)  
  
## <a name="see-also"></a><span data-ttu-id="ef354-124">См. также:</span><span class="sxs-lookup"><span data-stu-id="ef354-124">See Also</span></span>  
 <span data-ttu-id="ef354-125">[SQL Server Native Client &#40;OLE DB&#41;](../native-client/ole-db/sql-server-native-client-ole-db.md) </span><span class="sxs-lookup"><span data-stu-id="ef354-125">[SQL Server Native Client &#40;OLE DB&#41;](../native-client/ole-db/sql-server-native-client-ole-db.md) </span></span>  
 [<span data-ttu-id="ef354-126">Использование возвращающих табличные значения параметров &#40;OLE DB&#41;</span><span class="sxs-lookup"><span data-stu-id="ef354-126">Use Table-Valued Parameters &#40;OLE DB&#41;</span></span>](../native-client-ole-db-how-to/use-table-valued-parameters-ole-db.md)  
  
  
