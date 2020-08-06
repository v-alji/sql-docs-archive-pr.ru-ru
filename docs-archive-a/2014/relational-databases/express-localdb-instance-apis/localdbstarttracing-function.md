---
title: Функция ЛокалдбстарттраЦинг | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: reference
api_name:
- LocalDBStartTracing
api_location:
- sqluserinstance.dll
topic_type:
- apiref
ms.assetid: c7b83833-6d2a-4a06-9cb7-42767bed52c6
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: 1b10482e9839d43e29da72dbe2c194a01d8248eb
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87752164"
---
# <a name="localdbstarttracing-function"></a><span data-ttu-id="ee912-102">Функция LocalDBStartTracing</span><span class="sxs-lookup"><span data-stu-id="ee912-102">LocalDBStartTracing Function</span></span>
  <span data-ttu-id="ee912-103">Включает трассировку вызовов API для всех экземпляров SQL Server Express LocalDB, принадлежащих текущему пользователю Windows.</span><span class="sxs-lookup"><span data-stu-id="ee912-103">Enables tracing of API calls for all the SQL Server Express LocalDB instances owned by the current Windows user.</span></span>  
  
 <span data-ttu-id="ee912-104">**Файл заголовка:** sqlncli.h</span><span class="sxs-lookup"><span data-stu-id="ee912-104">**Header file:** sqlncli.h</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ee912-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="ee912-105">Syntax</span></span>  
  
```  
HRESULT LocalDBStartTracing();  
```  
  
## <a name="returns"></a><span data-ttu-id="ee912-106">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="ee912-106">Returns</span></span>  
 <span data-ttu-id="ee912-107">S_OK</span><span class="sxs-lookup"><span data-stu-id="ee912-107">S_OK</span></span>  
 <span data-ttu-id="ee912-108">Функция выполнена успешно.</span><span class="sxs-lookup"><span data-stu-id="ee912-108">The function succeeded.</span></span>  
  
 [<span data-ttu-id="ee912-109">LOCALDB_ERROR_XEVENT_FAILED</span><span class="sxs-lookup"><span data-stu-id="ee912-109">LOCALDB_ERROR_XEVENT_FAILED</span></span>](../express-localdb-error-messages/localdb-error-xevent-failed.md)  
 <span data-ttu-id="ee912-110">Не удалось запустить подсистему XEvent в API экземпляра LocalDB.</span><span class="sxs-lookup"><span data-stu-id="ee912-110">Failed to start XEvent engine within the LocalDB Instance API.</span></span>  
  
 [<span data-ttu-id="ee912-111">LOCALDB_ERROR_INTERNAL_ERROR</span><span class="sxs-lookup"><span data-stu-id="ee912-111">LOCALDB_ERROR_INTERNAL_ERROR</span></span>](../express-localdb-error-messages/localdb-error-internal-error.md)  
 <span data-ttu-id="ee912-112">Произошла непредвиденная ошибка.</span><span class="sxs-lookup"><span data-stu-id="ee912-112">An unexpected error occurred.</span></span> <span data-ttu-id="ee912-113">Подробные сведения см. в журнале событий.</span><span class="sxs-lookup"><span data-stu-id="ee912-113">See the event log for details.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ee912-114">Remarks</span><span class="sxs-lookup"><span data-stu-id="ee912-114">Remarks</span></span>  
 <span data-ttu-id="ee912-115">Образец кода, использующего API LocalDB, см. в разделе [SQL Server Express LocalDB Reference](../sql-server-express-localdb-reference.md)</span><span class="sxs-lookup"><span data-stu-id="ee912-115">For a code sample that uses LocalDB API, see [SQL Server Express LocalDB Reference](../sql-server-express-localdb-reference.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ee912-116">См. также:</span><span class="sxs-lookup"><span data-stu-id="ee912-116">See Also</span></span>  
 [<span data-ttu-id="ee912-117">Заголовок и сведения о версии SQL Server Express LocalDB</span><span class="sxs-lookup"><span data-stu-id="ee912-117">SQL Server Express LocalDB Header and Version Information</span></span>](sql-server-express-localdb-header-and-version-information.md)  
  
  
