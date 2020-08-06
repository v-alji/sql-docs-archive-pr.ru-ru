---
title: Функция LocalDBStopTracing | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: reference
api_name:
- LocalDBStopTracing
api_location:
- sqluserinstance.dll
topic_type:
- apiref
ms.assetid: 1d50e040-8602-4ffa-be8f-b8633fdfa7ff
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: 2bf6051fe8c86728c2ebf0a0b2bc34fabb98edb9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87655739"
---
# <a name="localdbstoptracing-function"></a><span data-ttu-id="9eb95-102">Функция LocalDBStopTracing</span><span class="sxs-lookup"><span data-stu-id="9eb95-102">LocalDBStopTracing Function</span></span>
  <span data-ttu-id="9eb95-103">Отключает трассировку вызовов API для всех экземпляров SQL Server Express LocalDB, принадлежащих текущему пользователю Windows.</span><span class="sxs-lookup"><span data-stu-id="9eb95-103">Disables tracing of API calls for all the SQL Server Express LocalDB instances owned by the current Windows user.</span></span>  
  
 <span data-ttu-id="9eb95-104">**Файл заголовка:** sqlncli.h</span><span class="sxs-lookup"><span data-stu-id="9eb95-104">**Header file:** sqlncli.h</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9eb95-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="9eb95-105">Syntax</span></span>  
  
```  
HRESULT LocalDBStopTracing();  
```  
  
## <a name="returns"></a><span data-ttu-id="9eb95-106">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="9eb95-106">Returns</span></span>  
 <span data-ttu-id="9eb95-107">S_OK</span><span class="sxs-lookup"><span data-stu-id="9eb95-107">S_OK</span></span>  
 <span data-ttu-id="9eb95-108">Функция выполнена успешно.</span><span class="sxs-lookup"><span data-stu-id="9eb95-108">The function succeeded.</span></span>  
  
 [<span data-ttu-id="9eb95-109">LOCALDB_ERROR_INTERNAL_ERROR</span><span class="sxs-lookup"><span data-stu-id="9eb95-109">LOCALDB_ERROR_INTERNAL_ERROR</span></span>](../express-localdb-error-messages/localdb-error-internal-error.md)  
 <span data-ttu-id="9eb95-110">Произошла непредвиденная ошибка.</span><span class="sxs-lookup"><span data-stu-id="9eb95-110">An unexpected error occurred.</span></span> <span data-ttu-id="9eb95-111">Подробные сведения см. в журнале событий.</span><span class="sxs-lookup"><span data-stu-id="9eb95-111">See the event log for details.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="9eb95-112">Remarks</span><span class="sxs-lookup"><span data-stu-id="9eb95-112">Remarks</span></span>  
 <span data-ttu-id="9eb95-113">Образец кода, использующего API LocalDB, см. в разделе [SQL Server Express LocalDB Reference](../sql-server-express-localdb-reference.md)</span><span class="sxs-lookup"><span data-stu-id="9eb95-113">For a code sample that uses LocalDB API, see [SQL Server Express LocalDB Reference](../sql-server-express-localdb-reference.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9eb95-114">См. также:</span><span class="sxs-lookup"><span data-stu-id="9eb95-114">See Also</span></span>  
 [<span data-ttu-id="9eb95-115">Заголовок и сведения о версии SQL Server Express LocalDB</span><span class="sxs-lookup"><span data-stu-id="9eb95-115">SQL Server Express LocalDB Header and Version Information</span></span>](sql-server-express-localdb-header-and-version-information.md)  
  
  
