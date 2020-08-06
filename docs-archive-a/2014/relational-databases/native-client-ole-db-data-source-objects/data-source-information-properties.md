---
title: Свойства сведений об источнике данных | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- SQL Server Native Client OLE DB provider, data source properties
- properties [OLE DB]
- data source properties [OLE DB]
- information properties [OLE DB]
- OLE DB data source properties [SQL Server Native Client]
ms.assetid: 7fd80e47-5bd9-41e2-a3d3-091a7c8c5f2b
author: rothja
ms.author: jroth
ms.openlocfilehash: c10a4e762bbe3421e720753941f5e0a5702832ad
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87749776"
---
# <a name="data-source-information-properties"></a><span data-ttu-id="f8012-102">Свойства сведений об источнике данных</span><span class="sxs-lookup"><span data-stu-id="f8012-102">Data Source Information Properties</span></span>
  <span data-ttu-id="f8012-103">В специфичном для каждого поставщика множестве свойств DBPROPSET_SQLSERVERDATASOURCEINFO поставщик OLE DB собственного клиента [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] определяет следующие свойства, хранящие информацию об источнике данных.</span><span class="sxs-lookup"><span data-stu-id="f8012-103">In the provider-specific property set DBPROPSET_SQLSERVERDATASOURCEINFO, the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider defines the following data source information properties.</span></span>  
  
|<span data-ttu-id="f8012-104">Идентификатор свойства</span><span class="sxs-lookup"><span data-stu-id="f8012-104">Property ID</span></span>|<span data-ttu-id="f8012-105">Описание</span><span class="sxs-lookup"><span data-stu-id="f8012-105">Description</span></span>|  
|-----------------|-----------------|  
|<span data-ttu-id="f8012-106">SSPROP_COLUMNLEVELCOLLATION</span><span class="sxs-lookup"><span data-stu-id="f8012-106">SSPROP_COLUMNLEVELCOLLATION</span></span>|<span data-ttu-id="f8012-107">Тип: VT_BOOL.</span><span class="sxs-lookup"><span data-stu-id="f8012-107">Type: VT_BOOL</span></span><br /><br /> <span data-ttu-id="f8012-108">Чтение и запись.</span><span class="sxs-lookup"><span data-stu-id="f8012-108">R/W: Read</span></span><br /><br /> <span data-ttu-id="f8012-109">Значение по умолчанию: VARIANT_TRUE</span><span class="sxs-lookup"><span data-stu-id="f8012-109">Default: VARIANT_TRUE</span></span><br /><br /> <span data-ttu-id="f8012-110">Описание: указывает, поддерживаются ли параметры сортировки столбцов.</span><span class="sxs-lookup"><span data-stu-id="f8012-110">Description: Used to determine if column collation is supported.</span></span><br /><br /> <span data-ttu-id="f8012-111">VARIANT_TRUE: параметры сортировки на уровне столбцов поддерживаются.</span><span class="sxs-lookup"><span data-stu-id="f8012-111">VARIANT_TRUE: Column level collation is supported.</span></span><br /><br /> <span data-ttu-id="f8012-112">VARIANT_FALSE: параметры сортировки на уровне столбцов не поддерживаются.</span><span class="sxs-lookup"><span data-stu-id="f8012-112">VARIANT_FALSE: Column level collation is not supported.</span></span>|  
|<span data-ttu-id="f8012-113">SSPROP_UNICODELCID</span><span class="sxs-lookup"><span data-stu-id="f8012-113">SSPROP_UNICODELCID</span></span>|<span data-ttu-id="f8012-114">Тип: VT_I4 R/W: чтение</span><span class="sxs-lookup"><span data-stu-id="f8012-114">Type: VT_I4 R/W: Read</span></span><br /><br /> <span data-ttu-id="f8012-115">Описание: идентификатор языка Юникода.</span><span class="sxs-lookup"><span data-stu-id="f8012-115">Description: Unicode locale ID.</span></span><br /><br /> <span data-ttu-id="f8012-116">Это локаль, используемый для сортировки данных в Юникоде.</span><span class="sxs-lookup"><span data-stu-id="f8012-116">This is the locale used for Unicode data sorting.</span></span>|  
|<span data-ttu-id="f8012-117">SSPROP_UNICODECOMPARISONSTYLE</span><span class="sxs-lookup"><span data-stu-id="f8012-117">SSPROP_UNICODECOMPARISONSTYLE</span></span>|<span data-ttu-id="f8012-118">Тип: VT_I4 R/W: чтение</span><span class="sxs-lookup"><span data-stu-id="f8012-118">Type: VT_I4 R/W: Read</span></span><br /><br /> <span data-ttu-id="f8012-119">Описание: стиль сравнения Юникода.</span><span class="sxs-lookup"><span data-stu-id="f8012-119">Description: Unicode comparison style.</span></span><br /><br /> <span data-ttu-id="f8012-120">Параметры сортировки, используемые для сортировки данных в Юникоде.</span><span class="sxs-lookup"><span data-stu-id="f8012-120">The sorting options used for Unicode data sorting.</span></span>|  
  
 <span data-ttu-id="f8012-121">В специфичном для каждого поставщика множестве свойств DBPROPSET_SQLSERVERSTREAM поставщик OLE DB собственного клиента [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] определяет следующее дополнительное свойство.</span><span class="sxs-lookup"><span data-stu-id="f8012-121">In the provider-specific property set DBPROPSET_SQLSERVERSTREAM, the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider defines the following additional property.</span></span>  
  
|<span data-ttu-id="f8012-122">Идентификатор свойства</span><span class="sxs-lookup"><span data-stu-id="f8012-122">Property ID</span></span>|<span data-ttu-id="f8012-123">Описание</span><span class="sxs-lookup"><span data-stu-id="f8012-123">Description</span></span>|  
|-----------------|-----------------|  
|<span data-ttu-id="f8012-124">SSPROP_STREAM_XMLROOT</span><span class="sxs-lookup"><span data-stu-id="f8012-124">SSPROP_STREAM_XMLROOT</span></span>|<span data-ttu-id="f8012-125">Тип: VT_BSTR R/W: чтение и запись</span><span class="sxs-lookup"><span data-stu-id="f8012-125">Type: VT_BSTR R/W: Read/Write</span></span><br /><br /> <span data-ttu-id="f8012-126">Описание: результат запроса FOR XML может не быть правильно сформированным документом.</span><span class="sxs-lookup"><span data-stu-id="f8012-126">Description: The result of a FOR XML query may not be a well-formed document.</span></span> <span data-ttu-id="f8012-127">Если это свойство задано, результат инструкции "select … for XML" окажется завернут в корневой тег, предоставленный данным свойством, для возвращения правильно сформированного XML-документа.</span><span class="sxs-lookup"><span data-stu-id="f8012-127">When this property is specified, the result of a 'select ... for XML' query is wrapped in the root tag provided by this property to return a well formed XML document.</span></span> <span data-ttu-id="f8012-128">Если запрос выполняется в браузере, при загрузке результата в окне браузера может быть выведена информация об ошибках средства синтаксического анализа.</span><span class="sxs-lookup"><span data-stu-id="f8012-128">If the query is executed in the browser it may cause the browser to display parser errors when loading the result.</span></span> <span data-ttu-id="f8012-129">Для избежания этой ошибки в SQL ISAPI применяется ключевое слово ROOT.</span><span class="sxs-lookup"><span data-stu-id="f8012-129">To avoid the error, SQL ISAPI supports the keyword ROOT.</span></span> <span data-ttu-id="f8012-130">Оно соответствует свойству SSPROP_STREAM_XMLROOT.</span><span class="sxs-lookup"><span data-stu-id="f8012-130">This keyword maps to SSPROP_STREAM_XMLROOT property.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="f8012-131">См. также:</span><span class="sxs-lookup"><span data-stu-id="f8012-131">See Also</span></span>  
 [<span data-ttu-id="f8012-132">Объекты источников данных (OLE DB)</span><span class="sxs-lookup"><span data-stu-id="f8012-132">Data Source Objects &#40;OLE DB&#41;</span></span>](data-source-objects-ole-db.md)  
  
  
