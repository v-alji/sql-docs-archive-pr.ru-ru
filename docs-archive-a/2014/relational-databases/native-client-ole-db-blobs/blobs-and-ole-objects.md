---
title: Большие двоичные объекты и объекты OLE | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- BLOBs, OLE objects
- BLOBs
- storage object [OLE DB]
- SQL Server Native Client OLE DB provider, BLOBs
- large data, OLE objects
ms.assetid: 767fa2f6-9cd2-436f-add5-e760bed29a58
author: rothja
ms.author: jroth
ms.openlocfilehash: 15f8b4915ba9b05a5be19854a2e27a2e8ff3a346
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87750823"
---
# <a name="blobs-and-ole-objects"></a><span data-ttu-id="be073-102">Большие двоичные объекты и объекты OLE</span><span class="sxs-lookup"><span data-stu-id="be073-102">BLOBs and OLE Objects</span></span>
  <span data-ttu-id="be073-103">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]Поставщик OLE DB собственного клиента предоставляет интерфейс **ISequentialStream** для поддержки доступа потребителя к [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] типам данных **ntext**, **Text**, **Image**, **varchar (max)**, **nvarchar (max)**, **varbinary (max)** и XML в виде больших двоичных объектов (BLOB).</span><span class="sxs-lookup"><span data-stu-id="be073-103">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider exposes the **ISequentialStream** interface to support consumer access to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] **ntext**, **text**, **image**, **varchar(max)**, **nvarchar(max)**, **varbinary(max)**, and xml data types as binary large objects (BLOBs).</span></span> <span data-ttu-id="be073-104">Метод **Read** интерфейса **ISequentialStream** позволяет потребителю получать большой объем данных в виде фрагментов данных, с которыми удобно работать.</span><span class="sxs-lookup"><span data-stu-id="be073-104">The **Read** method on **ISequentialStream** lets the consumer retrieve much data in manageable chunks.</span></span>  
  
 <span data-ttu-id="be073-105">Образец приложения, демонстрирующий эту возможность, см. в статье [Задание данных больших объектов (OLE DB)](../native-client-ole-db-how-to/set-large-data-ole-db.md).</span><span class="sxs-lookup"><span data-stu-id="be073-105">For a sample demonstrating this feature, see [Set Large Data &#40;OLE DB&#41;](../native-client-ole-db-how-to/set-large-data-ole-db.md).</span></span>  
  
 <span data-ttu-id="be073-106">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]Поставщик OLE DB собственного клиента может использовать реализуемый потребителем интерфейс **IStorage** , когда потребитель предоставляет указатель интерфейса в методе доступа, связанном с изменением данных.</span><span class="sxs-lookup"><span data-stu-id="be073-106">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider can use a consumer-implemented **IStorage** interface when the consumer provides the interface pointer in an accessor bound for data modification.</span></span>  
  
 <span data-ttu-id="be073-107">Для типов данных больших значений [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] поставщик собственного клиента OLE DB проверяет предположения о размере типов в интерфейсах **IROWSET** и DDL.</span><span class="sxs-lookup"><span data-stu-id="be073-107">For large value data types, the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider checks for type size assumptions in **IRowset** and DDL interfaces.</span></span> <span data-ttu-id="be073-108">Столбцы с типами данных **varchar**, **nvarchar**и **varbinary** с максимальным размером, установленным в значение unlimited, будут представлены как длинные через наборы строк схемы и интерфейсы, возвращающие типы данных столбцов.</span><span class="sxs-lookup"><span data-stu-id="be073-108">Columns with **varchar**, **nvarchar**, and **varbinary** data types with max size set to unlimited will be represented as ISLONG through the schema rowsets and interfaces returning column data types.</span></span>  
  
 <span data-ttu-id="be073-109">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]Поставщик OLE DB собственного клиента предоставляет типы **varchar (max)**, **varbinary (max)** и **nvarchar (max)** как DBTYPE_STR, DBTYPE_BYTES и DBTYPE_WSTR соответственно.</span><span class="sxs-lookup"><span data-stu-id="be073-109">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider exposes the **varchar(max)**, **varbinary(max)** and **nvarchar(max)** types as DBTYPE_STR, DBTYPE_BYTES and DBTYPE_WSTR respectively.</span></span>  
  
 <span data-ttu-id="be073-110">Для работы с этими типами приложение имеет следующие возможности.</span><span class="sxs-lookup"><span data-stu-id="be073-110">To work with these types an application has the following options:</span></span>  
  
-   <span data-ttu-id="be073-111">Выполните привязку, указав тип (DBTYPE_STR, DBTYPE_BYTES, DBTYPE_WSTR).</span><span class="sxs-lookup"><span data-stu-id="be073-111">Bind as the type (DBTYPE_STR, DBTYPE_BYTES, DBTYPE_WSTR).</span></span> <span data-ttu-id="be073-112">Если буфер недостаточно большой, будет выполнено усечение — точно так же, как в предыдущих версиях (хотя сейчас доступны большие значения).</span><span class="sxs-lookup"><span data-stu-id="be073-112">If the buffer is not big enough truncation will occur, exactly as for these types in previous releases (although larger values are now available).</span></span>  
  
-   <span data-ttu-id="be073-113">Выполните привязку, указав тип и задав DBTYPE_BYREF.</span><span class="sxs-lookup"><span data-stu-id="be073-113">Bind as the type and also specify DBTYPE_BYREF.</span></span>  
  
-   <span data-ttu-id="be073-114">Выполните привязку, указав тип DBTYPE_IUNKNOWN, и используйте потоковую передачу.</span><span class="sxs-lookup"><span data-stu-id="be073-114">Bind as DBTYPE_IUNKNOWN and use streaming.</span></span>  
  
 <span data-ttu-id="be073-115">При привязке к DBTYPE_IUNKNOWN используется потоковая возможность ISequentialStream.</span><span class="sxs-lookup"><span data-stu-id="be073-115">If bound to DBTYPE_IUNKNOWN, ISequentialStream stream functionality is used.</span></span> <span data-ttu-id="be073-116">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]Поставщик OLE DB собственного клиента поддерживает привязку выходных параметров как DBTYPE_IUNKNOWN для типов данных больших значений, чтобы упростить сценарии, в которых хранимая процедура возвращает эти типы данных в виде возвращаемых значений, которые будут предоставлены клиенту как DBTYPE_IUNKNOWN.</span><span class="sxs-lookup"><span data-stu-id="be073-116">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider supports binding output parameters as DBTYPE_IUNKNOWN for large value data types to facilitate scenarios where a stored procedure returns these data types as return values which will be exposed as DBTYPE_IUNKNOWN to the client.</span></span>  
  
## <a name="storage-object-limitations"></a><span data-ttu-id="be073-117">Ограничения объекта хранилища</span><span class="sxs-lookup"><span data-stu-id="be073-117">Storage Object Limitations</span></span>  
  
-   <span data-ttu-id="be073-118">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]Поставщик OLE DB собственного клиента может поддерживать только один открытый объект хранилища.</span><span class="sxs-lookup"><span data-stu-id="be073-118">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider can support only a single open storage object.</span></span> <span data-ttu-id="be073-119">При попытке открыть несколько объектов хранилища (получить ссылку на несколько указателей интерфейса **ISequentialStream**) возвращается DBSTATUS_E_CANTCREATE.</span><span class="sxs-lookup"><span data-stu-id="be073-119">Attempts to open more than one storage object (to get a reference on more than one **ISequentialStream** interface pointer) return DBSTATUS_E_CANTCREATE.</span></span>  
  
-   <span data-ttu-id="be073-120">В [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] поставщике OLE DB собственного клиента значением свойства DBPROP_BLOCKINGSTORAGEOBJECTS только для чтения является VARIANT_TRUE.</span><span class="sxs-lookup"><span data-stu-id="be073-120">In the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider, the default value of the DBPROP_BLOCKINGSTORAGEOBJECTS read-only property is VARIANT_TRUE.</span></span> <span data-ttu-id="be073-121">Оно указывает, что если имеется активный объект хранилища, некоторые методы (не относящиеся к объектам хранилища) завершатся ошибкой E_UNEXPECTED.</span><span class="sxs-lookup"><span data-stu-id="be073-121">This indicates that if a storage object is active, some methods (other than those on the storage objects) will fail with E_UNEXPECTED.</span></span>  
  
-   <span data-ttu-id="be073-122">Длина данных, представленных объектом хранилища, реализованным потребителем, должна быть известна [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] поставщику OLE DB собственного клиента при создании метода доступа к строке, ссылающегося на объект хранилища.</span><span class="sxs-lookup"><span data-stu-id="be073-122">The length of data presented by a consumer-implemented storage object must be made known to the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider when the row accessor that references the storage object is created.</span></span> <span data-ttu-id="be073-123">Потребитель должен выполнить привязку признака длины в структуре DBBINDING, которая используется для создания метода доступа.</span><span class="sxs-lookup"><span data-stu-id="be073-123">The consumer must bind a length indicator in the DBBINDING structure used for accessor creation.</span></span>  
  
-   <span data-ttu-id="be073-124">Если строка содержит больше одного большого значения данных, а DBPROP_ACCESSORDER не DBPROPVAL_AO_RANDOM, потребитель должен либо использовать [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] собственный клиент OLE DBный набор строк с поддержкой курсора поставщика, чтобы получить данные строк или обработать все большие значения данных перед получением других значений строк.</span><span class="sxs-lookup"><span data-stu-id="be073-124">If a row contains more than a single large data value and DBPROP_ACCESSORDER is not DBPROPVAL_AO_RANDOM, the consumer must either use a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider cursor-supported rowset to retrieve row data or process all large data values before retrieving other row values.</span></span> <span data-ttu-id="be073-125">Если DBPROP_ACCESSORDER DBPROPVAL_AO_RANDOM, то [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] поставщик OLE DB собственного клиента кэширует все типы данных XML как большие двоичные объекты (BLOB), чтобы к ним можно было обращаться в любом порядке.</span><span class="sxs-lookup"><span data-stu-id="be073-125">If DBPROP_ACCESSORDER is DBPROPVAL_AO_RANDOM, the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider caches all the xml data types as binary large objects (BLOBs) so that it can be accessed in any order.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="be073-126">в этом разделе</span><span class="sxs-lookup"><span data-stu-id="be073-126">In This Section</span></span>  
  
-   [<span data-ttu-id="be073-127">Возврат больших данных</span><span class="sxs-lookup"><span data-stu-id="be073-127">Getting Large Data</span></span>](getting-large-data.md)  
  
-   [<span data-ttu-id="be073-128">Присваивание больших данных</span><span class="sxs-lookup"><span data-stu-id="be073-128">Setting Large Data</span></span>](setting-large-data.md)  
  
-   [<span data-ttu-id="be073-129">Поддержка потоков для выходных параметров BLOB</span><span class="sxs-lookup"><span data-stu-id="be073-129">Streaming Support for BLOB Output Parameters</span></span>](streaming-support-for-blob-output-parameters.md)  
  
## <a name="see-also"></a><span data-ttu-id="be073-130">См. также:</span><span class="sxs-lookup"><span data-stu-id="be073-130">See Also</span></span>  
 <span data-ttu-id="be073-131">[SQL Server Native Client &#40;OLE DB&#41;](../native-client/ole-db/sql-server-native-client-ole-db.md) </span><span class="sxs-lookup"><span data-stu-id="be073-131">[SQL Server Native Client &#40;OLE DB&#41;](../native-client/ole-db/sql-server-native-client-ole-db.md) </span></span>  
 [<span data-ttu-id="be073-132">Использование типов больших значений</span><span class="sxs-lookup"><span data-stu-id="be073-132">Using Large Value Types</span></span>](../native-client/features/using-large-value-types.md)  
  
  
