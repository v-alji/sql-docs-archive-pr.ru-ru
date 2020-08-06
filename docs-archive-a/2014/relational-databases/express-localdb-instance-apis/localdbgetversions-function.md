---
title: Функция Локалдбжетверсионс | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: reference
api_name:
- LocalDBGetVersions
api_location:
- sqluserinstance.dll
topic_type:
- apiref
ms.assetid: 033a9c6b-0d7f-4f8a-ab60-33cd6fee0d33
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: 37d2a927346252f1b126f5e3a4ec78ea03cde0a6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87749955"
---
# <a name="localdbgetversions-function"></a><span data-ttu-id="c7fff-102">Функция LocalDBGetVersions</span><span class="sxs-lookup"><span data-stu-id="c7fff-102">LocalDBGetVersions Function</span></span>
  <span data-ttu-id="c7fff-103">Возвращает все доступные версии SQL Server Express LocalDB на компьютере.</span><span class="sxs-lookup"><span data-stu-id="c7fff-103">Returns all SQL Server Express LocalDB versions available on the computer.</span></span>  
  
 <span data-ttu-id="c7fff-104">**Файл заголовка:** sqlncli.h</span><span class="sxs-lookup"><span data-stu-id="c7fff-104">**Header file:** sqlncli.h</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c7fff-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="c7fff-105">Syntax</span></span>  
  
```  
#define MAX_LOCALDB_VERSION_LENGTH 43typedef WCHAR TLocalDBVersion[MAX_LOCALDB_VERSION_LENGTH + 1];typedef TLocalDBVersion* PTLocalDBVersion;HRESULT LocalDBGetVersions(           PTLocalDBVersion pVersion,           LPDWORD lpdwNumberOfVersions);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c7fff-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="c7fff-106">Parameters</span></span>  
 <span data-ttu-id="c7fff-107">*pVersionNames*</span><span class="sxs-lookup"><span data-stu-id="c7fff-107">*pVersionNames*</span></span>  
 <span data-ttu-id="c7fff-108">Проверки Содержит имена версий LocalDB, доступных на рабочей станции пользователя.</span><span class="sxs-lookup"><span data-stu-id="c7fff-108">[Output] Contains names of the LocalDB versions that are available on the user's workstation.</span></span>  
  
 <span data-ttu-id="c7fff-109">*лпдвнумберофверсионс*</span><span class="sxs-lookup"><span data-stu-id="c7fff-109">*lpdwNumberOfVersions*</span></span>  
 <span data-ttu-id="c7fff-110">[Вход/выход] На входе содержит число ячеек для версий в буфере *pVersionNames* .</span><span class="sxs-lookup"><span data-stu-id="c7fff-110">[Input/Output] On input holds the number of slots for versions in the *pVersionNames* buffer.</span></span>   
<span data-ttu-id="c7fff-111">На выходе содержит количество существующих версий LocalDB.</span><span class="sxs-lookup"><span data-stu-id="c7fff-111">On output, holds the number of existing LocalDB versions.</span></span>  
  
## <a name="returns"></a><span data-ttu-id="c7fff-112">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="c7fff-112">Returns</span></span>  
 <span data-ttu-id="c7fff-113">S_OK</span><span class="sxs-lookup"><span data-stu-id="c7fff-113">S_OK</span></span>  
 <span data-ttu-id="c7fff-114">Функция выполнена успешно.</span><span class="sxs-lookup"><span data-stu-id="c7fff-114">The function succeeded.</span></span>  
  
 [<span data-ttu-id="c7fff-115">LOCALDB_ERROR_NOT_INSTALLED</span><span class="sxs-lookup"><span data-stu-id="c7fff-115">LOCALDB_ERROR_NOT_INSTALLED</span></span>](../express-localdb-error-messages/localdb-error-not-installed.md)  
 <span data-ttu-id="c7fff-116">Компонент SQL Server Express LocalDB не установлен на компьютере.</span><span class="sxs-lookup"><span data-stu-id="c7fff-116">SQL Server Express LocalDB is not installed on the computer.</span></span>  
  
 [<span data-ttu-id="c7fff-117">LOCALDB_ERROR_INVALID_PARAMETER</span><span class="sxs-lookup"><span data-stu-id="c7fff-117">LOCALDB_ERROR_INVALID_PARAMETER</span></span>](../express-localdb-error-messages/localdb-error-invalid-parameter.md)  
 <span data-ttu-id="c7fff-118">Один или несколько указанных входных параметров недопустимы.</span><span class="sxs-lookup"><span data-stu-id="c7fff-118">One or more specified input parameters are invalid.</span></span>  
  
 [<span data-ttu-id="c7fff-119">LOCALDB_ERROR_INSUFFICIENT_BUFFER</span><span class="sxs-lookup"><span data-stu-id="c7fff-119">LOCALDB_ERROR_INSUFFICIENT_BUFFER</span></span>](../express-localdb-error-messages/localdb-error-insufficient-buffer.md)  
 <span data-ttu-id="c7fff-120">Размер входного буфера является недостаточным, а усечение не было запрошено.</span><span class="sxs-lookup"><span data-stu-id="c7fff-120">The input buffer is too short, and truncation was not requested.</span></span>  
  
 [<span data-ttu-id="c7fff-121">LOCALDB_ERROR_INTERNAL_ERROR</span><span class="sxs-lookup"><span data-stu-id="c7fff-121">LOCALDB_ERROR_INTERNAL_ERROR</span></span>](../express-localdb-error-messages/localdb-error-internal-error.md)  
 <span data-ttu-id="c7fff-122">Произошла непредвиденная ошибка.</span><span class="sxs-lookup"><span data-stu-id="c7fff-122">An unexpected error occurred.</span></span> <span data-ttu-id="c7fff-123">Подробные сведения см. в журнале событий.</span><span class="sxs-lookup"><span data-stu-id="c7fff-123">See the event log for details.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c7fff-124">Remarks</span><span class="sxs-lookup"><span data-stu-id="c7fff-124">Remarks</span></span>  
 <span data-ttu-id="c7fff-125">Образец кода, использующего API LocalDB, см. в разделе [SQL Server Express LocalDB Reference](../sql-server-express-localdb-reference.md)</span><span class="sxs-lookup"><span data-stu-id="c7fff-125">For a code sample that uses LocalDB API, see [SQL Server Express LocalDB Reference](../sql-server-express-localdb-reference.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c7fff-126">См. также:</span><span class="sxs-lookup"><span data-stu-id="c7fff-126">See Also</span></span>  
 [<span data-ttu-id="c7fff-127">Заголовок и сведения о версии SQL Server Express LocalDB</span><span class="sxs-lookup"><span data-stu-id="c7fff-127">SQL Server Express LocalDB Header and Version Information</span></span>](sql-server-express-localdb-header-and-version-information.md)  
  
  
