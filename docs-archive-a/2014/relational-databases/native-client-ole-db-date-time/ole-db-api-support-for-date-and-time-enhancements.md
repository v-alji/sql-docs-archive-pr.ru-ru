---
title: Новые возможности поддержки API OLE DB для функций даты и времени | Документы Майкрософт
ms.custom: ''
ms.date: 04/27/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: reference
helpviewer_keywords:
- OLE DB, date/time improvements
ms.assetid: e65c9253-bd99-4dc3-9cb8-7613f754c966
author: rothja
ms.author: jroth
ms.openlocfilehash: cdb17f0d2104373ea797ff9403cc417dfaa3d868
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87667069"
---
# <a name="ole-db-api-support-for-date-and-time-enhancements"></a><span data-ttu-id="79cfb-102">Новые возможности поддержки API OLE DB для функций даты и времени</span><span class="sxs-lookup"><span data-stu-id="79cfb-102">OLE DB API Support for Date and Time Enhancements</span></span>
  <span data-ttu-id="79cfb-103">Следующие API-интерфейсы OLE DB поддерживают улучшенные возможности по работе с данными в формате даты-времени.</span><span class="sxs-lookup"><span data-stu-id="79cfb-103">The following OLE DB APIs support enhanced date/time features.</span></span>  
  
|<span data-ttu-id="79cfb-104">Функция</span><span class="sxs-lookup"><span data-stu-id="79cfb-104">Function</span></span>|<span data-ttu-id="79cfb-105">Описание</span><span class="sxs-lookup"><span data-stu-id="79cfb-105">Description</span></span>|  
|--------------|-----------------|  
|<span data-ttu-id="79cfb-106">IAccessor::CreateAccessor</span><span class="sxs-lookup"><span data-stu-id="79cfb-106">IAccessor::CreateAccessor</span></span>|<span data-ttu-id="79cfb-107">Чтобы позволить приложениям различать значения `datetime`, `datetime2` и `smalldatetime`, в структуру DBBINDING добавляется флаг.</span><span class="sxs-lookup"><span data-stu-id="79cfb-107">A flag is added in the DBBINDING structure to enable applications to discriminate between `datetime`, `datetime2`, and `smalldatetime` values.</span></span> <span data-ttu-id="79cfb-108">Дополнительные сведения см. в статье [Метаданные — параметры и наборы строк](metadata-parameter-and-rowset.md).</span><span class="sxs-lookup"><span data-stu-id="79cfb-108">For more information, see [Parameter and Rowset Metadata](metadata-parameter-and-rowset.md).</span></span>|  
|<span data-ttu-id="79cfb-109">IBCPSession::BCPColFmt</span><span class="sxs-lookup"><span data-stu-id="79cfb-109">IBCPSession::BCPColFmt</span></span>|<span data-ttu-id="79cfb-110">Дополнительные сведения см. в статье [инструкции по расширенному копированию для улучшенных типов даты и времени &#40;OLE DB и ODBC&#41;](../native-client-odbc-date-time/bulk-copy-changes-for-enhanced-date-and-time-types-ole-db-and-odbc.md).</span><span class="sxs-lookup"><span data-stu-id="79cfb-110">For more information, see [Bulk Copy Changes for Enhanced Date and Time Types &#40;OLE DB and ODBC&#41;](../native-client-odbc-date-time/bulk-copy-changes-for-enhanced-date-and-time-types-ole-db-and-odbc.md).</span></span>|  
|<span data-ttu-id="79cfb-111">ICommandWithParameters::GetParameterInfo</span><span class="sxs-lookup"><span data-stu-id="79cfb-111">ICommandWithParameters::GetParameterInfo</span></span>|<span data-ttu-id="79cfb-112">Дополнительные сведения см. в статье [Метаданные — параметры и наборы строк](metadata-parameter-and-rowset.md).</span><span class="sxs-lookup"><span data-stu-id="79cfb-112">For more information, see[Parameter and Rowset Metadata](metadata-parameter-and-rowset.md).</span></span>|  
|<span data-ttu-id="79cfb-113">ICommandWithParameters::SetParameterinfo</span><span class="sxs-lookup"><span data-stu-id="79cfb-113">ICommandWithParameters::SetParameterinfo</span></span>|<span data-ttu-id="79cfb-114">Дополнительные сведения см. в статье [Метаданные — параметры и наборы строк](metadata-parameter-and-rowset.md).</span><span class="sxs-lookup"><span data-stu-id="79cfb-114">For more information, see[Parameter and Rowset Metadata](metadata-parameter-and-rowset.md).</span></span>|  
|<span data-ttu-id="79cfb-115">IColumnsRowset::GetColumnsRowset</span><span class="sxs-lookup"><span data-stu-id="79cfb-115">IColumnsRowset::GetColumnsRowset</span></span>|<span data-ttu-id="79cfb-116">Дополнительные сведения см. в статье [Метаданные — параметры и наборы строк](metadata-parameter-and-rowset.md).</span><span class="sxs-lookup"><span data-stu-id="79cfb-116">For more information, see[Parameter and Rowset Metadata](metadata-parameter-and-rowset.md).</span></span>|  
|<span data-ttu-id="79cfb-117">IColumnsInfo::GetColumnInfo</span><span class="sxs-lookup"><span data-stu-id="79cfb-117">IColumnsInfo::GetColumnInfo</span></span>|<span data-ttu-id="79cfb-118">Дополнительные сведения см. в статье [Метаданные — параметры и наборы строк](metadata-parameter-and-rowset.md).</span><span class="sxs-lookup"><span data-stu-id="79cfb-118">For more information, see[Parameter and Rowset Metadata](metadata-parameter-and-rowset.md).</span></span>|  
|<span data-ttu-id="79cfb-119">IDBSchemaRowset::GetRowset</span><span class="sxs-lookup"><span data-stu-id="79cfb-119">IDBSchemaRowset::GetRowset</span></span>|<span data-ttu-id="79cfb-120">Подробности о затронутых наборах строк схемы см. в статье [Метаданные — наборы строк даты и времени и схемы](../native-client-ole-db-rowsets/rowsets.md).</span><span class="sxs-lookup"><span data-stu-id="79cfb-120">For details of the affected schema rowsets, see[Date and Time and Schema Rowsets](../native-client-ole-db-rowsets/rowsets.md).</span></span>|  
|<span data-ttu-id="79cfb-121">IRowsetFastLoad</span><span class="sxs-lookup"><span data-stu-id="79cfb-121">IRowsetFastLoad</span></span>|<span data-ttu-id="79cfb-122">Данный интерфейс поддерживает новые типы даты-времени, но он остается неизменным.</span><span class="sxs-lookup"><span data-stu-id="79cfb-122">This interface supports the new date/time types, but there is no change to its interface.</span></span>|  
|<span data-ttu-id="79cfb-123">ITableDefinition::CreateTable</span><span class="sxs-lookup"><span data-stu-id="79cfb-123">ITableDefinition::CreateTable</span></span>|<span data-ttu-id="79cfb-124">Подробнее см. статью [Улучшения поддержки типов данных даты и времени OLE DB](data-type-support-for-ole-db-date-and-time-improvements.md).</span><span class="sxs-lookup"><span data-stu-id="79cfb-124">For more information, see [Data Type Support for OLE DB Date and Time Improvements](data-type-support-for-ole-db-date-and-time-improvements.md).</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="79cfb-125">См. также:</span><span class="sxs-lookup"><span data-stu-id="79cfb-125">See Also</span></span>  
 [<span data-ttu-id="79cfb-126">Улучшения функций даты и времени &#40;OLE DB&#41;</span><span class="sxs-lookup"><span data-stu-id="79cfb-126">Date and Time Improvements &#40;OLE DB&#41;</span></span>](date-and-time-improvements-ole-db.md)  
  
  
