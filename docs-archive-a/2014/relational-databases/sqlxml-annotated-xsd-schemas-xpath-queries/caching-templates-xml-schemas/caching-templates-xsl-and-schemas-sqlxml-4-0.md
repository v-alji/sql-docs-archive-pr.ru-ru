---
title: Кэширование шаблонов, XSL и схем (SQLXML 4,0) | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: reference
helpviewer_keywords:
- SQLXML, caching
- cache [SQLXML]
- memory [SQLXML]
ms.assetid: 80b4fa79-243f-442c-9f22-74ad66186501
author: rothja
ms.author: jroth
ms.openlocfilehash: 4df25909cf156957908abf0691964fd66a76343a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87665256"
---
# <a name="caching-templates-xsl-and-schemas-sqlxml-40"></a><span data-ttu-id="7b1c3-102">Кэширование шаблонов, XSL и схем (SQLXML 4.0)</span><span class="sxs-lookup"><span data-stu-id="7b1c3-102">Caching Templates, XSL, and Schemas (SQLXML 4.0)</span></span>
  <span data-ttu-id="7b1c3-103">Для повышения производительности [!INCLUDE[msCoName](../../../includes/msconame-md.md)] SQLXML 4.0 поддерживает кэширование шаблонов, XSL и схем.</span><span class="sxs-lookup"><span data-stu-id="7b1c3-103">To improve performance, [!INCLUDE[msCoName](../../../includes/msconame-md.md)] SQLXML 4.0 supports caching templates, XSL, and schemas.</span></span>  
  
 <span data-ttu-id="7b1c3-104">Все файлы схем, шаблонов и XSL-файлы (кроме файлов с местонахождением http:// или ftp://) кэшируются.</span><span class="sxs-lookup"><span data-stu-id="7b1c3-104">All schemas, templates, and XSL files (except the files from an http:// or ftp:// location) are cached.</span></span> <span data-ttu-id="7b1c3-105">Кэшированные файлы остаются в памяти, пока процесс выполняется.</span><span class="sxs-lookup"><span data-stu-id="7b1c3-105">The cached files remain in memory while the process is running.</span></span> <span data-ttu-id="7b1c3-106">При завершении процесса содержимое кэша уничтожается.</span><span class="sxs-lookup"><span data-stu-id="7b1c3-106">As the process exits, all the cache is lost.</span></span> <span data-ttu-id="7b1c3-107">Поэтому, если в запросе выполняется один процесс, выигрыш от кэширования может быть незначителен.</span><span class="sxs-lookup"><span data-stu-id="7b1c3-107">Therefore, if you run one process per query, the caching benefit may not be noticeable.</span></span>  
  
 <span data-ttu-id="7b1c3-108">Подразделы этого раздела содержат дополнительные сведения о кэшировании.</span><span class="sxs-lookup"><span data-stu-id="7b1c3-108">The topics in this section provide more information about caching.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="7b1c3-109">в этом разделе</span><span class="sxs-lookup"><span data-stu-id="7b1c3-109">In This Section</span></span>  
 [<span data-ttu-id="7b1c3-110">Кэширование шаблонов &#40;SQLXML 4,0&#41;</span><span class="sxs-lookup"><span data-stu-id="7b1c3-110">Template Caching &#40;SQLXML 4.0&#41;</span></span>](template-caching-sqlxml-4-0.md)  
 <span data-ttu-id="7b1c3-111">Описывается кэширование шаблонов и приводится соответствующий раздел реестра.</span><span class="sxs-lookup"><span data-stu-id="7b1c3-111">Describes and provides a registry key for template caching.</span></span>  
  
 [<span data-ttu-id="7b1c3-112">Кэширование XSL &#40;SQLXML 4,0&#41;</span><span class="sxs-lookup"><span data-stu-id="7b1c3-112">XSL Caching &#40;SQLXML 4.0&#41;</span></span>](xsl-caching-sqlxml-4-0.md)  
 <span data-ttu-id="7b1c3-113">Описывается кэширование XSL и приводится соответствующий раздел реестра.</span><span class="sxs-lookup"><span data-stu-id="7b1c3-113">Describes and provides a registry key for XSL caching.</span></span>  
  
 [<span data-ttu-id="7b1c3-114">Кэширование схемы &#40;SQLXML 4,0&#41;</span><span class="sxs-lookup"><span data-stu-id="7b1c3-114">Schema Caching &#40;SQLXML 4.0&#41;</span></span>](schema-caching-sqlxml-4-0.md)  
 <span data-ttu-id="7b1c3-115">Обсуждаются вопросы параллельной установки SQLXML, связанные с кэшированием схем, и приводятся соответствующие разделы реестра.</span><span class="sxs-lookup"><span data-stu-id="7b1c3-115">Discusses SQLXML side-by-side installation issues related to schema caching, and provides registry keys for schema caching.</span></span>  
  
  
