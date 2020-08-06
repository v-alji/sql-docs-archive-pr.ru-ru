---
title: IRowsetFastLoad::InsertRow (OLE DB) | Документация Майкрософт
ms.custom: ''
ms.date: 03/09/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
api_name:
- IRowsetFastLoad::InsertRow (OLE DB)
topic_type:
- apiref
helpviewer_keywords:
- InsertRow method
ms.assetid: 594d3461-34d2-41e7-8ad4-bd2753601ab6
author: rothja
ms.author: jroth
ms.openlocfilehash: 4e9ea952f27574270ee333919f778814ff3de462
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87667702"
---
# <a name="irowsetfastloadinsertrow-ole-db"></a><span data-ttu-id="0d380-102">IRowsetFastLoad::InsertRow (OLE DB)</span><span class="sxs-lookup"><span data-stu-id="0d380-102">IRowsetFastLoad::InsertRow (OLE DB)</span></span>
  <span data-ttu-id="0d380-103">Добавляет строку в набор строк для массового копирования.</span><span class="sxs-lookup"><span data-stu-id="0d380-103">Adds a row to the bulk copy rowset.</span></span> <span data-ttu-id="0d380-104">Примеры можно найти в статьях [Выполнение массового копирования данных с использованием интерфейса IRowsetFastLoad (OLE DB)](../native-client-ole-db-how-to/bulk-copy-data-using-irowsetfastload-ole-db.md) и [Отправка данных BLOB-объектов в SQL Server с помощью интерфейсов IROWSETFASTLOAD и ISEQUENTIALSTREAM (OLE DB)](../native-client-ole-db-how-to/send-blob-data-to-sql-server-using-irowsetfastload-and-isequentialstream-ole-db.md)</span><span class="sxs-lookup"><span data-stu-id="0d380-104">For samples, see [Bulk Copy Data Using IRowsetFastLoad &#40;OLE DB&#41;](../native-client-ole-db-how-to/bulk-copy-data-using-irowsetfastload-ole-db.md) and [Send BLOB Data to SQL SERVER Using IROWSETFASTLOAD and ISEQUENTIALSTREAM &#40;OLE DB&#41;](../native-client-ole-db-how-to/send-blob-data-to-sql-server-using-irowsetfastload-and-isequentialstream-ole-db.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0d380-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="0d380-105">Syntax</span></span>  
  
```  
  
HRESULT InsertRow(  
HACCESSOR  
hAccessor  
,  
void*  
pData  
);  
  
```  
  
## <a name="arguments"></a><span data-ttu-id="0d380-106">Аргументы</span><span class="sxs-lookup"><span data-stu-id="0d380-106">Arguments</span></span>  
 <span data-ttu-id="0d380-107">*hAccessor*[in]</span><span class="sxs-lookup"><span data-stu-id="0d380-107">*hAccessor*[in]</span></span>  
 <span data-ttu-id="0d380-108">Дескриптор метода доступа, определяющий данные строк для массового копирования.</span><span class="sxs-lookup"><span data-stu-id="0d380-108">The handle of the accessor defining the row data for bulk copy.</span></span> <span data-ttu-id="0d380-109">Указанный метод доступа является методом доступа к строке, связывающий память потребителя, содержащую значения данных.</span><span class="sxs-lookup"><span data-stu-id="0d380-109">The accessor referenced is a row accessor, binding consumer-owned memory containing data values.</span></span>  
  
 <span data-ttu-id="0d380-110">*pData*[in]</span><span class="sxs-lookup"><span data-stu-id="0d380-110">*pData*[in]</span></span>  
 <span data-ttu-id="0d380-111">Указатель на память потребителя, содержащую значения данных.</span><span class="sxs-lookup"><span data-stu-id="0d380-111">A pointer to the consumer-owned memory containing data values.</span></span> <span data-ttu-id="0d380-112">Дополнительные сведения см. в разделе [Структуры DBBINDING](https://go.microsoft.com/fwlink/?LinkId=65955).</span><span class="sxs-lookup"><span data-stu-id="0d380-112">For more information, see [DBBINDING Structures](https://go.microsoft.com/fwlink/?LinkId=65955).</span></span>  
  
## <a name="return-code-values"></a><span data-ttu-id="0d380-113">Значения кода возврата</span><span class="sxs-lookup"><span data-stu-id="0d380-113">Return Code Values</span></span>  
 <span data-ttu-id="0d380-114">S_OK</span><span class="sxs-lookup"><span data-stu-id="0d380-114">S_OK</span></span>  
 <span data-ttu-id="0d380-115">Метод выполнен успешно.</span><span class="sxs-lookup"><span data-stu-id="0d380-115">The method succeeded.</span></span> <span data-ttu-id="0d380-116">Любые связанные значения состояния для всех столбцов имеют значение DBSTATUS_S_OK или DBSTATUS_S_NULL.</span><span class="sxs-lookup"><span data-stu-id="0d380-116">Any bound status values for all columns have value DBSTATUS_S_OK or DBSTATUS_S_NULL.</span></span>  
  
 <span data-ttu-id="0d380-117">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="0d380-117">E_FAIL</span></span>  
 <span data-ttu-id="0d380-118">Произошла ошибка.</span><span class="sxs-lookup"><span data-stu-id="0d380-118">An error occurred.</span></span> <span data-ttu-id="0d380-119">Сведения об ошибках можно получить с помощью интерфейса обработки ошибок набора строк.</span><span class="sxs-lookup"><span data-stu-id="0d380-119">Error information is available from the rowset's error interfaces.</span></span>  
  
 <span data-ttu-id="0d380-120">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="0d380-120">E_INVALIDARG</span></span>  
 <span data-ttu-id="0d380-121">Аргумент *pData* содержит указатель NULL.</span><span class="sxs-lookup"><span data-stu-id="0d380-121">The *pData* argument was set to a NULL pointer.</span></span>  
  
 <span data-ttu-id="0d380-122">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="0d380-122">E_OUTOFMEMORY</span></span>  
 <span data-ttu-id="0d380-123">SQLNCLI11 не удалось выделить достаточно памяти для завершения запроса.</span><span class="sxs-lookup"><span data-stu-id="0d380-123">SQLNCLI11 was unable to allocate sufficient memory to complete the request.</span></span>  
  
 <span data-ttu-id="0d380-124">E_UNEXPECTED</span><span class="sxs-lookup"><span data-stu-id="0d380-124">E_UNEXPECTED</span></span>  
 <span data-ttu-id="0d380-125">Этот метод был вызван применительно к набору строк массового копирования, который ранее стал недействительным в результате выполнения метода [IRowsetFastLoad::Commit](irowsetfastload-commit-ole-db.md).</span><span class="sxs-lookup"><span data-stu-id="0d380-125">The method was called on a bulk copy rowset previously invalidated by the [IRowsetFastLoad::Commit](irowsetfastload-commit-ole-db.md) method.</span></span>  
  
 <span data-ttu-id="0d380-126">DB_E_BADACCESSORHANDLE</span><span class="sxs-lookup"><span data-stu-id="0d380-126">DB_E_BADACCESSORHANDLE</span></span>  
 <span data-ttu-id="0d380-127">Потребитель предоставил недопустимый аргумент *hAccessor* .</span><span class="sxs-lookup"><span data-stu-id="0d380-127">The *hAccessor* argument provided by the consumer was invalid.</span></span>  
  
 <span data-ttu-id="0d380-128">DB_E_BADACCESSORTYPE</span><span class="sxs-lookup"><span data-stu-id="0d380-128">DB_E_BADACCESSORTYPE</span></span>  
 <span data-ttu-id="0d380-129">Указанный метод доступа не является методом доступа к строке или не указывает память потребителя.</span><span class="sxs-lookup"><span data-stu-id="0d380-129">The specified accessor was not a row accessor or did not specify consumer-owned memory.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="0d380-130">Remarks</span><span class="sxs-lookup"><span data-stu-id="0d380-130">Remarks</span></span>  
 <span data-ttu-id="0d380-131">Ошибка при преобразовании данных потребителя в тип данных [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] для столбца приводит к тому, что поставщик OLE DB для собственного клиента [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] возвращает E_FAIL.</span><span class="sxs-lookup"><span data-stu-id="0d380-131">An error converting consumer data to the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] data type for a column causes an E_FAIL return from the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider.</span></span> <span data-ttu-id="0d380-132">Данные могут передаваться в [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] любым методом **InsertRow** или только методом **Commit**.</span><span class="sxs-lookup"><span data-stu-id="0d380-132">Data can be transmitted to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] on any **InsertRow** method or only on **Commit** method.</span></span> <span data-ttu-id="0d380-133">Приложение потребителя может вызывать метод **InsertRow** много раз с ошибочными данными, прежде чем получит уведомление, что при преобразовании типов данных произошла ошибка.</span><span class="sxs-lookup"><span data-stu-id="0d380-133">The consumer application can call the **InsertRow** method many times with erroneous data before it receives notice that a data type conversion error exists.</span></span> <span data-ttu-id="0d380-134">Поскольку метод **Commit** гарантирует, что все данные были правильно указаны потребителем, потребитель может при необходимости использовать метод **Commit** для проверки данных.</span><span class="sxs-lookup"><span data-stu-id="0d380-134">Because the **Commit** method ensures that all data is correctly specified by the consumer, the consumer can use the **Commit** method appropriately to validate data as necessary.</span></span>  
  
 <span data-ttu-id="0d380-135">Наборы строк для массового копирования поставщиком OLE DB для собственного клиента [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] доступны только для записи.</span><span class="sxs-lookup"><span data-stu-id="0d380-135">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider bulk copy rowsets are write-only.</span></span> <span data-ttu-id="0d380-136">Поставщик OLE DB для собственного клиента [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] не предоставляет методов, позволяющих потребителю запрашивать наборы строк.</span><span class="sxs-lookup"><span data-stu-id="0d380-136">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider exposes no methods allowing consumer query of the rowset.</span></span> <span data-ttu-id="0d380-137">Чтобы прервать обработку, потребитель может освободить ссылку на интерфейс [IRowsetFastLoad](irowsetfastload-ole-db.md), не вызывая метод **Commit**.</span><span class="sxs-lookup"><span data-stu-id="0d380-137">To terminate processing, the consumer can release its reference on the [IRowsetFastLoad](irowsetfastload-ole-db.md) interface without calling the **Commit** method.</span></span> <span data-ttu-id="0d380-138">Невозможно получить доступ к вставленной потребителем строке, изменить ее значения или удалить ее из набора строк.</span><span class="sxs-lookup"><span data-stu-id="0d380-138">There are no facilities for accessing a consumer-inserted row in the rowset and changing its values, or removing it individually from the rowset.</span></span>  
  
 <span data-ttu-id="0d380-139">Массово скопированные строки форматируются на сервере для [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="0d380-139">Bulk copied rows are formatted on the server for [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="0d380-140">Формат строки зависит от любых параметров, которые могли быть заданы для соединения или сеанса, например ANSI_PADDING.</span><span class="sxs-lookup"><span data-stu-id="0d380-140">The row format is affected by any options that may have been set for the connection or session such as ANSI_PADDING.</span></span> <span data-ttu-id="0d380-141">Этот параметр по умолчанию включен для любого соединения, установленного с помощью поставщика OLE DB для собственного клиента [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="0d380-141">This option is set on by default for any connection made through the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0d380-142">См. также:</span><span class="sxs-lookup"><span data-stu-id="0d380-142">See Also</span></span>  
 [<span data-ttu-id="0d380-143">IRowsetFastLoad &#40;OLE DB&#41;</span><span class="sxs-lookup"><span data-stu-id="0d380-143">IRowsetFastLoad &#40;OLE DB&#41;</span></span>](irowsetfastload-ole-db.md)  
  
  
