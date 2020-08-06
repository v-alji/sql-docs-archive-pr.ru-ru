---
title: Категория событий OLEDB | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
topic_type:
- apiref
helpviewer_keywords:
- OLEDB event category
- SQL Server event classes, OLEDB event category
- event classes [SQL Server], OLEDB event category
ms.assetid: cf93e424-3dac-462d-b3da-92e7d0b064d4
author: stevestein
ms.author: sstein
ms.openlocfilehash: bd55294966448f8976dc20198381918e163cc0d7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87657114"
---
# <a name="oledb-event-category"></a><span data-ttu-id="08bbb-102">OLEDB, категория событий</span><span class="sxs-lookup"><span data-stu-id="08bbb-102">OLEDB Event Category</span></span>
  <span data-ttu-id="08bbb-103">Категория событий **OLEDB** содержит общие события OLEDB.</span><span class="sxs-lookup"><span data-stu-id="08bbb-103">The **OLEDB** event category contains general OLEDB events.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="08bbb-104">в этом разделе</span><span class="sxs-lookup"><span data-stu-id="08bbb-104">In This Section</span></span>  
  
|<span data-ttu-id="08bbb-105">Раздел</span><span class="sxs-lookup"><span data-stu-id="08bbb-105">Topic</span></span>|<span data-ttu-id="08bbb-106">Description</span><span class="sxs-lookup"><span data-stu-id="08bbb-106">Description</span></span>|  
|-----------|-----------------|  
|[<span data-ttu-id="08bbb-107">Класс событий OLEDB Call</span><span class="sxs-lookup"><span data-stu-id="08bbb-107">OLEDB Call Event Class</span></span>](oledb-call-event-class.md)|<span data-ttu-id="08bbb-108">Указывает, что [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] запросил распределенные запросы и удаленные хранимые процедуры у поставщика OLE DB путем вызова, не связанного с данными, или вызова, не связанного с**QueryInterface**.</span><span class="sxs-lookup"><span data-stu-id="08bbb-108">Indicates that [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] has made a non-data or non-**QueryInterface** call to an OLE DB provider for distributed queries and remote stored procedures.</span></span>|  
|[<span data-ttu-id="08bbb-109">Класс событий OLEDB DataRead</span><span class="sxs-lookup"><span data-stu-id="08bbb-109">OLEDB DataRead Event Class</span></span>](oledb-dataread-event-class.md)|<span data-ttu-id="08bbb-110">Указывает, что [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] запросил у поставщика OLE DB распределенные запросы и удаленные хранимые процедуры.</span><span class="sxs-lookup"><span data-stu-id="08bbb-110">Indicates that [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] has called an OLE DB provider for distributed queries and remote stored procedures.</span></span>|  
|[<span data-ttu-id="08bbb-111">Класс событий OLEDB Errors</span><span class="sxs-lookup"><span data-stu-id="08bbb-111">OLEDB Errors Event Class</span></span>](oledb-errors-event-class.md)|<span data-ttu-id="08bbb-112">Указывает, что вызов поставщика OLE DB возвратил ошибку.</span><span class="sxs-lookup"><span data-stu-id="08bbb-112">Indicates that a call to an OLE DB provider returned an error.</span></span>|  
|[<span data-ttu-id="08bbb-113">Класс событий OLEDB Provider Information</span><span class="sxs-lookup"><span data-stu-id="08bbb-113">OLEDB Provider Information Event Class</span></span>](oledb-provider-information-event-class.md)|<span data-ttu-id="08bbb-114">Указывает, что распределенный запрос был выполнен и собрал сведения, соответствующие соединению поставщика.</span><span class="sxs-lookup"><span data-stu-id="08bbb-114">Indicates that a distributed query has run and has collected information that corresponds to the provider connection.</span></span>|  
|[<span data-ttu-id="08bbb-115">Класс событий OLEDB QueryInterface</span><span class="sxs-lookup"><span data-stu-id="08bbb-115">OLEDB QueryInterface Event Class</span></span>](oledb-queryinterface-event-class.md)|<span data-ttu-id="08bbb-116">Указывает, что [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] запросил у поставщика OLE DB распределенные запросы и удаленные хранимые процедуры путем вызова **QueryInterface** .</span><span class="sxs-lookup"><span data-stu-id="08bbb-116">Indicates that [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] has issued an OLE DB **QueryInterface** call for distributed queries and remote stored procedures.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="08bbb-117">См. также:</span><span class="sxs-lookup"><span data-stu-id="08bbb-117">See Also</span></span>  
 [<span data-ttu-id="08bbb-118">Расширенные события</span><span class="sxs-lookup"><span data-stu-id="08bbb-118">Extended Events</span></span>](../extended-events/extended-events.md)  
  
  
