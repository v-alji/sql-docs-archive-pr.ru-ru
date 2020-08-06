---
title: Сравнимость для IRowsetFind | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: reference
helpviewer_keywords:
- IRowsetFind comparability [ODBC]
ms.assetid: 7d148b56-9bbe-4e55-b31f-43f115705402
author: rothja
ms.author: jroth
ms.openlocfilehash: 8ad359ca4957b434c3798d1a441eb0fd57644a59
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87656387"
---
# <a name="comparability-for-irowsetfind"></a><span data-ttu-id="094a7-102">Сравнимость для IRowsetFind</span><span class="sxs-lookup"><span data-stu-id="094a7-102">Comparability for IRowsetFind</span></span>
  <span data-ttu-id="094a7-103">Интерфейс IRowsetFind поддерживает следующие сравнения (только для типов даты-времени).</span><span class="sxs-lookup"><span data-stu-id="094a7-103">For date/time types only, IRowsetFind supports the following comparisons:</span></span>  
  
-   <span data-ttu-id="094a7-104">LT</span><span class="sxs-lookup"><span data-stu-id="094a7-104">LT</span></span>  
  
-   <span data-ttu-id="094a7-105">LE</span><span class="sxs-lookup"><span data-stu-id="094a7-105">LE</span></span>  
  
-   <span data-ttu-id="094a7-106">EQ</span><span class="sxs-lookup"><span data-stu-id="094a7-106">EQ</span></span>  
  
-   <span data-ttu-id="094a7-107">GE</span><span class="sxs-lookup"><span data-stu-id="094a7-107">GE</span></span>  
  
-   <span data-ttu-id="094a7-108">GT</span><span class="sxs-lookup"><span data-stu-id="094a7-108">GT</span></span>  
  
-   <span data-ttu-id="094a7-109">NE</span><span class="sxs-lookup"><span data-stu-id="094a7-109">NE</span></span>  
  
-   <span data-ttu-id="094a7-110">IGNORE</span><span class="sxs-lookup"><span data-stu-id="094a7-110">IGNORE</span></span>  
  
 <span data-ttu-id="094a7-111">При попытке любого другого сравнения возвращается ошибка DB_E_BADCOMPAREOP.</span><span class="sxs-lookup"><span data-stu-id="094a7-111">If any other comparison is attempted, DB_E_BADCOMPAREOP is returned.</span></span> <span data-ttu-id="094a7-112">Это согласуется со спецификацией OLE DB.</span><span class="sxs-lookup"><span data-stu-id="094a7-112">This is consistent with the OLE DB specification.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="094a7-113">См. также:</span><span class="sxs-lookup"><span data-stu-id="094a7-113">See Also</span></span>  
 [<span data-ttu-id="094a7-114">Улучшения функций даты и времени &#40;OLE DB&#41;</span><span class="sxs-lookup"><span data-stu-id="094a7-114">Date and Time Improvements &#40;OLE DB&#41;</span></span>](date-and-time-improvements-ole-db.md)  
  
  
