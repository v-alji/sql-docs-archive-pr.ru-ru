---
title: DISCOVER_XEVENT_TRACE_DEFINITION набор строк | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: reference
ms.assetid: e1ce2d2d-f994-4318-801a-ee0385aecd84
author: minewiskan
ms.author: owend
ms.openlocfilehash: bedd6ec66a188738ac9a522b4802b3b431e82f36
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87734566"
---
# <a name="discover_xevent_trace_definition-rowset"></a><span data-ttu-id="f6f7b-102">Набор строк DISCOVER_XEVENT_TRACE_DEFINITION</span><span class="sxs-lookup"><span data-stu-id="f6f7b-102">DISCOVER_XEVENT_TRACE_DEFINITION Rowset</span></span>
  <span data-ttu-id="f6f7b-103">Содержит сведения о трассировках XEvent, которые в настоящее время активны на сервере.</span><span class="sxs-lookup"><span data-stu-id="f6f7b-103">Provides information about XEvent traces that are currently active on the server.</span></span>  
  
 <span data-ttu-id="f6f7b-104">**Область применения:** табличные модели, многомерные модели</span><span class="sxs-lookup"><span data-stu-id="f6f7b-104">**Applies to:** tabular models, multidimensional models</span></span>  
  
## <a name="rowset-columns"></a><span data-ttu-id="f6f7b-105">Столбцы наборов строк</span><span class="sxs-lookup"><span data-stu-id="f6f7b-105">Rowset Columns</span></span>  
 <span data-ttu-id="f6f7b-106">Набор строк `DISCOVER_XEVENT_TRACE_DEFINITION` содержит следующие столбцы.</span><span class="sxs-lookup"><span data-stu-id="f6f7b-106">The `DISCOVER_XEVENT_TRACE_DEFINITION` rowset contains the following columns.</span></span>  
  
|<span data-ttu-id="f6f7b-107">Имя столбца</span><span class="sxs-lookup"><span data-stu-id="f6f7b-107">Column name</span></span>|<span data-ttu-id="f6f7b-108">Индикатор типа</span><span class="sxs-lookup"><span data-stu-id="f6f7b-108">Type indicator</span></span>|<span data-ttu-id="f6f7b-109">Длина</span><span class="sxs-lookup"><span data-stu-id="f6f7b-109">Length</span></span>|<span data-ttu-id="f6f7b-110">Описание</span><span class="sxs-lookup"><span data-stu-id="f6f7b-110">Description</span></span>|  
|-----------------|--------------------|------------|-----------------|  
|`Data`|`DBTYPE_WSTR`||<span data-ttu-id="f6f7b-111">XML-определение трассировки XEvent.</span><span class="sxs-lookup"><span data-stu-id="f6f7b-111">The XML definition of the XEvent trace.</span></span>|  
  
 <span data-ttu-id="f6f7b-112">Этот набор строк схемы не отсортирован.</span><span class="sxs-lookup"><span data-stu-id="f6f7b-112">This schema rowset is not sorted.</span></span>  
  
## <a name="using-adomdnet-to-return-the-rowset"></a><span data-ttu-id="f6f7b-113">Использование ADOMD.NET для возврата набора строк</span><span class="sxs-lookup"><span data-stu-id="f6f7b-113">Using ADOMD.NET to return the rowset</span></span>  
 <span data-ttu-id="f6f7b-114">Если для получения метаданных используется ADOMD.NET и набор строк схемы, то для ссылки на объект набора строк схемы в методе GetSchemaDataSet вы можете использовать идентификатор GUID или строку.</span><span class="sxs-lookup"><span data-stu-id="f6f7b-114">When using ADOMD.NET and the schema rowset to retrieve metadata, you can use either the GUID or string to reference a schema rowset object in the GetSchemaDataSet method.</span></span> <span data-ttu-id="f6f7b-115">Дополнительные сведения см. в статье [Working with Schema Rowsets in ADOMD.NET](https://docs.microsoft.com/bi-reference/adomd/multidimensional-models-adomd-net-client/retrieving-metadata-working-with-schema-rowsets).</span><span class="sxs-lookup"><span data-stu-id="f6f7b-115">For more information, see [Working with Schema Rowsets in ADOMD.NET](https://docs.microsoft.com/bi-reference/adomd/multidimensional-models-adomd-net-client/retrieving-metadata-working-with-schema-rowsets).</span></span>  
  
 <span data-ttu-id="f6f7b-116">В следующей таблице указываются значения строки и идентификатора GUID, определяющие этот набор строк.</span><span class="sxs-lookup"><span data-stu-id="f6f7b-116">The following table provides the GUID and string values that identify this rowset.</span></span>  
  
|<span data-ttu-id="f6f7b-117">Аргумент</span><span class="sxs-lookup"><span data-stu-id="f6f7b-117">Argument</span></span>|<span data-ttu-id="f6f7b-118">Значение</span><span class="sxs-lookup"><span data-stu-id="f6f7b-118">Value</span></span>|  
|--------------|-----------|  
|<span data-ttu-id="f6f7b-119">Код GUID</span><span class="sxs-lookup"><span data-stu-id="f6f7b-119">GUID</span></span>|<span data-ttu-id="f6f7b-120">a07ccd1c-8148-11d0-87bb-00c04fc33942</span><span class="sxs-lookup"><span data-stu-id="f6f7b-120">a07ccd1c-8148-11d0-87bb-00c04fc33942</span></span>|  
|<span data-ttu-id="f6f7b-121">Строка</span><span class="sxs-lookup"><span data-stu-id="f6f7b-121">String</span></span>|<span data-ttu-id="f6f7b-122">DISCOVER_XEVENT_TRACE_DEFINITION</span><span class="sxs-lookup"><span data-stu-id="f6f7b-122">DISCOVER_XEVENT_TRACE_DEFINITION</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="f6f7b-123">См. также:</span><span class="sxs-lookup"><span data-stu-id="f6f7b-123">See Also</span></span>  
 <span data-ttu-id="f6f7b-124">[XML для аналитики наборов строк схемы](https://docs.microsoft.com/bi-reference/schema-rowsets/xml/xml-for-analysis-schema-rowsets) </span><span class="sxs-lookup"><span data-stu-id="f6f7b-124">[XML for Analysis Schema Rowsets](https://docs.microsoft.com/bi-reference/schema-rowsets/xml/xml-for-analysis-schema-rowsets) </span></span>  
 <span data-ttu-id="f6f7b-125">[Используйте SQL Server расширенные события &#40;&#41; XEvents для отслеживания Analysis Services](../instances/monitor-analysis-services-with-sql-server-extended-events.md) </span><span class="sxs-lookup"><span data-stu-id="f6f7b-125">[Use SQL Server Extended Events &#40;XEvents&#41; to Monitor Analysis Services](../instances/monitor-analysis-services-with-sql-server-extended-events.md) </span></span>  
 [<span data-ttu-id="f6f7b-126">Использование динамических административных представлений для мониторинга служб Analysis Services</span><span class="sxs-lookup"><span data-stu-id="f6f7b-126">Use Dynamic Management Views &#40;DMVs&#41; to Monitor Analysis Services</span></span>](../instances/use-dynamic-management-views-dmvs-to-monitor-analysis-services.md)  
  
  
