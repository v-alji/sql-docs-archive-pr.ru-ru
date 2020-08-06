---
title: Набор строк LINKEDSERVERS (OLE DB) | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- LINKEDSERVERS rowset
- enumerating data sources [OLE DB]
ms.assetid: 2633fd8a-65e7-498d-9aed-8e4b1cca2381
author: rothja
ms.author: jroth
ms.openlocfilehash: 80eded31ebae744e272757a53a7fd1f4b56bf358
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87656364"
---
# <a name="linkedservers-rowset-ole-db"></a><span data-ttu-id="d82cc-102">Набор строк LINKEDSERVERS (OLE DB)</span><span class="sxs-lookup"><span data-stu-id="d82cc-102">LINKEDSERVERS Rowset (OLE DB)</span></span>
  <span data-ttu-id="d82cc-103">Набор строк **LINKEDSERVERS** перечисляет источники данных организации, которые могут применяться в распределенных запросах [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="d82cc-103">The **LINKEDSERVERS** rowset enumerates organization data sources that can participate in [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] distributed queries.</span></span>  
  
 <span data-ttu-id="d82cc-104">Набор строк **LINKEDSERVERS** содержит следующие столбцы.</span><span class="sxs-lookup"><span data-stu-id="d82cc-104">The **LINKEDSERVERS** rowset contains the following columns.</span></span>  
  
|<span data-ttu-id="d82cc-105">Имя столбца</span><span class="sxs-lookup"><span data-stu-id="d82cc-105">Column name</span></span>|<span data-ttu-id="d82cc-106">Индикатор типа</span><span class="sxs-lookup"><span data-stu-id="d82cc-106">Type indicator</span></span>|<span data-ttu-id="d82cc-107">Описание</span><span class="sxs-lookup"><span data-stu-id="d82cc-107">Description</span></span>|  
|-----------------|--------------------|-----------------|  
|<span data-ttu-id="d82cc-108">SVR_NAME</span><span class="sxs-lookup"><span data-stu-id="d82cc-108">SVR_NAME</span></span>|<span data-ttu-id="d82cc-109">DBTYPE_WSTR</span><span class="sxs-lookup"><span data-stu-id="d82cc-109">DBTYPE_WSTR</span></span>|<span data-ttu-id="d82cc-110">Имя связанного сервера.</span><span class="sxs-lookup"><span data-stu-id="d82cc-110">Name of a linked server.</span></span>|  
|<span data-ttu-id="d82cc-111">SVR_PRODUCT</span><span class="sxs-lookup"><span data-stu-id="d82cc-111">SVR_PRODUCT</span></span>|<span data-ttu-id="d82cc-112">DBTYPE_WSTR</span><span class="sxs-lookup"><span data-stu-id="d82cc-112">DBTYPE_WSTR</span></span>|<span data-ttu-id="d82cc-113">Имя производителя или другое имя, задающее тип хранилища данных, представленного именем связанного сервера.</span><span class="sxs-lookup"><span data-stu-id="d82cc-113">Manufacturer or other name identifying the type of data store represented by the name of the linked server.</span></span>|  
|<span data-ttu-id="d82cc-114">SVR_PROVIDERNAME</span><span class="sxs-lookup"><span data-stu-id="d82cc-114">SVR_PROVIDERNAME</span></span>|<span data-ttu-id="d82cc-115">DBTYPE_WSTR</span><span class="sxs-lookup"><span data-stu-id="d82cc-115">DBTYPE_WSTR</span></span>|<span data-ttu-id="d82cc-116">Понятное имя поставщика OLE DB, используемого для получения данных с этого сервера.</span><span class="sxs-lookup"><span data-stu-id="d82cc-116">Friendly name of the OLE DB provider used to consume data from the server.</span></span>|  
|<span data-ttu-id="d82cc-117">SVR_DATASOURCE</span><span class="sxs-lookup"><span data-stu-id="d82cc-117">SVR_DATASOURCE</span></span>|<span data-ttu-id="d82cc-118">DBTYPE_WSTR</span><span class="sxs-lookup"><span data-stu-id="d82cc-118">DBTYPE_WSTR</span></span>|<span data-ttu-id="d82cc-119">Строка OLE DB DBPROP_INIT_DATASOURCE, используемая для получения источника данных от поставщика.</span><span class="sxs-lookup"><span data-stu-id="d82cc-119">OLE DB DBPROP_INIT_DATASOURCE string used to acquire a data source from the provider.</span></span>|  
|<span data-ttu-id="d82cc-120">SVR_PROVIDERSTRING</span><span class="sxs-lookup"><span data-stu-id="d82cc-120">SVR_PROVIDERSTRING</span></span>|<span data-ttu-id="d82cc-121">DBTYPE_WSTR</span><span class="sxs-lookup"><span data-stu-id="d82cc-121">DBTYPE_WSTR</span></span>|<span data-ttu-id="d82cc-122">Значение OLE DB DBPROP_INIT_PROVIDERSTRING, используемое для получения источника данных от поставщика.</span><span class="sxs-lookup"><span data-stu-id="d82cc-122">OLE DB DBPROP_INIT_PROVIDERSTRING value used to acquire a data source from the provider.</span></span>|  
|<span data-ttu-id="d82cc-123">SVR_LOCATION</span><span class="sxs-lookup"><span data-stu-id="d82cc-123">SVR_LOCATION</span></span>|<span data-ttu-id="d82cc-124">DBTYPE_WSTR</span><span class="sxs-lookup"><span data-stu-id="d82cc-124">DBTYPE_WSTR</span></span>|<span data-ttu-id="d82cc-125">Строка OLE DB DBPROP_INIT_LOCATION, используемая для получения источника данных от поставщика.</span><span class="sxs-lookup"><span data-stu-id="d82cc-125">OLE DB DBPROP_INIT_LOCATION string used to acquire a data source from the provider.</span></span>|  
  
 <span data-ttu-id="d82cc-126">Набор строк сортируется по столбцу SRV_NAME, и единственное ограничение поддерживается для столбца SRV_NAME.</span><span class="sxs-lookup"><span data-stu-id="d82cc-126">The rowset is sorted on SRV_NAME and a single restriction is supported on SRV_NAME.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d82cc-127">См. также:</span><span class="sxs-lookup"><span data-stu-id="d82cc-127">See Also</span></span>  
 [<span data-ttu-id="d82cc-128">Поддержка набора строк схемы &#40;OLE DB&#41;</span><span class="sxs-lookup"><span data-stu-id="d82cc-128">Schema Rowset Support &#40;OLE DB&#41;</span></span>](schema-rowset-support-ole-db.md)  
  
  
