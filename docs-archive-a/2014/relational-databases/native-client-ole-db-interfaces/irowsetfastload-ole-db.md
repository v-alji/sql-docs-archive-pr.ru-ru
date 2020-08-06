---
title: IRowsetFastLoad (OLE DB) | Документация Майкрософт
ms.custom: ''
ms.date: 04/27/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
topic_type:
- apiref
helpviewer_keywords:
- IRowsetFastLoad interface
ms.assetid: d19a7097-48d9-409a-aff9-277891b7aca7
author: rothja
ms.author: jroth
ms.openlocfilehash: 7ecf72f0015d9ed197b3b7a33d4f9bb3246134b1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87667701"
---
# <a name="irowsetfastload-ole-db"></a><span data-ttu-id="7b70e-102">Метод IRowsetFastLoad (OLE DB)</span><span class="sxs-lookup"><span data-stu-id="7b70e-102">IRowsetFastLoad (OLE DB)</span></span>
  <span data-ttu-id="7b70e-103">`IRowsetFastLoad`Интерфейс обеспечивает поддержку операций с [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] массовым копированием на основе памяти.</span><span class="sxs-lookup"><span data-stu-id="7b70e-103">The `IRowsetFastLoad` interface exposes support for [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] memory-based bulk-copy operations.</span></span> [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]<span data-ttu-id="7b70e-104">Потребители поставщика собственного клиента OLE DB используют интерфейс для быстрого добавления данных в существующую [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] таблицу.</span><span class="sxs-lookup"><span data-stu-id="7b70e-104">Native Client OLE DB provider consumers use the interface to rapidly add data to an existing [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] table.</span></span>  
  
 <span data-ttu-id="7b70e-105">Если присвоить SSPROP_ENABLEFASTLOAD значение VARIANT_TRUE для сеанса, то будет невозможно считывать данные из наборов строк, возвращаемых впоследствии в этом сеансе.</span><span class="sxs-lookup"><span data-stu-id="7b70e-105">If you set SSPROP_ENABLEFASTLOAD to VARIANT_TRUE for a session, you cannot read data from rowsets subsequently returned from that session.</span></span> <span data-ttu-id="7b70e-106">Если присвоить SSPROP_ENABLEFASTLOAD значение VARIANT_TRUE, то все наборы строк, созданные для сеанса, будут иметь тип IRowsetFastLoad.</span><span class="sxs-lookup"><span data-stu-id="7b70e-106">When SSPROP_ENABLEFASTLOAD is set to VARIANT_TRUE, all rowsets created on the session will be of type IRowsetFastLoad.</span></span> <span data-ttu-id="7b70e-107">Наборы строк IRowsetFastLoad не поддерживают функциональные возможности получения данных из набора строк, поэтому чтение данных из наборов строк невозможно.</span><span class="sxs-lookup"><span data-stu-id="7b70e-107">IRowsetFastLoad rowsets do not support rowset fetch functionality; therefore, data from these rowsets cannot be read.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="7b70e-108">в этом разделе</span><span class="sxs-lookup"><span data-stu-id="7b70e-108">In This Section</span></span>  
  
|<span data-ttu-id="7b70e-109">Метод</span><span class="sxs-lookup"><span data-stu-id="7b70e-109">Method</span></span>|<span data-ttu-id="7b70e-110">Описание</span><span class="sxs-lookup"><span data-stu-id="7b70e-110">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="7b70e-111">IRowsetFastLoad::Commit (OLE DB)</span><span class="sxs-lookup"><span data-stu-id="7b70e-111">IRowsetFastLoad::Commit &#40;OLE DB&#41;</span></span>](irowsetfastload-commit-ole-db.md)|<span data-ttu-id="7b70e-112">Обозначает конец пакета вставляемых строк и записывает эти строки в таблицу [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="7b70e-112">Marks the end of a batch of inserted rows and writes the rows to the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] table.</span></span>|  
|[<span data-ttu-id="7b70e-113">IRowsetFastLoad::InsertRow (OLE DB)</span><span class="sxs-lookup"><span data-stu-id="7b70e-113">IRowsetFastLoad::InsertRow &#40;OLE DB&#41;</span></span>](irowsetfastload-insertrow-ole-db.md)|<span data-ttu-id="7b70e-114">Добавляет строку в набор строк для массового копирования.</span><span class="sxs-lookup"><span data-stu-id="7b70e-114">Adds a row to the bulk copy rowset.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="7b70e-115">См. также:</span><span class="sxs-lookup"><span data-stu-id="7b70e-115">See Also</span></span>  
 <span data-ttu-id="7b70e-116">[Интерфейсы &#40;OLE DB&#41;](../../database-engine/dev-guide/interfaces-ole-db.md) </span><span class="sxs-lookup"><span data-stu-id="7b70e-116">[Interfaces &#40;OLE DB&#41;](../../database-engine/dev-guide/interfaces-ole-db.md) </span></span>  
 <span data-ttu-id="7b70e-117">[Групповое Копирование данных с использованием IRowsetFastLoad &#40;OLE DB&#41;](../native-client-ole-db-how-to/bulk-copy-data-using-irowsetfastload-ole-db.md) </span><span class="sxs-lookup"><span data-stu-id="7b70e-117">[Bulk Copy Data Using IRowsetFastLoad &#40;OLE DB&#41;](../native-client-ole-db-how-to/bulk-copy-data-using-irowsetfastload-ole-db.md) </span></span>  
 [<span data-ttu-id="7b70e-118">Отправка данных BLOB-объектов в SQL Server с помощью интерфейсов IROWSETFASTLOAD и ISEQUENTIALSTREAM &#40;OLE DB&#41;</span><span class="sxs-lookup"><span data-stu-id="7b70e-118">Send BLOB Data to SQL SERVER Using IROWSETFASTLOAD and ISEQUENTIALSTREAM &#40;OLE DB&#41;</span></span>](../native-client-ole-db-how-to/send-blob-data-to-sql-server-using-irowsetfastload-and-isequentialstream-ole-db.md)  
  
  
