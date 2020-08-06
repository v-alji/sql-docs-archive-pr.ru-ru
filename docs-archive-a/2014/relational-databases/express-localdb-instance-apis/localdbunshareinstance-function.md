---
title: Функция Локалдбуншареинстанце | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: reference
api_name:
- LocalDBUnshareInstance
api_location:
- sqluserinstance.dll
topic_type:
- apiref
ms.assetid: 54012ccb-eded-43f7-8ea5-da5ce79224c6
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: 77ebf8cad9d410b047fccede4360ca0041637986
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87655740"
---
# <a name="localdbunshareinstance-function"></a><span data-ttu-id="6334b-102">Функция LocalDBUnshareInstance</span><span class="sxs-lookup"><span data-stu-id="6334b-102">LocalDBUnshareInstance Function</span></span>
  <span data-ttu-id="6334b-103">Останавливает совместный доступ к указанному экземпляру SQL Server Express LocalDB.</span><span class="sxs-lookup"><span data-stu-id="6334b-103">Stops the sharing of the specified SQL Server Express LocalDB instance.</span></span>  
  
 <span data-ttu-id="6334b-104">**Файл заголовка:** sqlncli.h</span><span class="sxs-lookup"><span data-stu-id="6334b-104">**Header file:** sqlncli.h</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6334b-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="6334b-105">Syntax</span></span>  
  
```  
HRESULT LocalDBUnShareInstance(  
           PCWSTR pInstanceSharedName,   
           DWORD dwFlags   
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="6334b-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="6334b-106">Parameters</span></span>  
 <span data-ttu-id="6334b-107">*пинстанцешареднаме*</span><span class="sxs-lookup"><span data-stu-id="6334b-107">*pInstanceSharedName*</span></span>  
 <span data-ttu-id="6334b-108">[Вход] Общее имя экземпляра LocalDB, для которого отключается совместный доступ.</span><span class="sxs-lookup"><span data-stu-id="6334b-108">[Input] The shared name for the LocalDB instance to unshare.</span></span>  
  
 <span data-ttu-id="6334b-109">*dwFlags*</span><span class="sxs-lookup"><span data-stu-id="6334b-109">*dwFlags*</span></span>  
 <span data-ttu-id="6334b-110">[Вход] Зарезервировано для использования в будущем.</span><span class="sxs-lookup"><span data-stu-id="6334b-110">[Input] Reserved for future use.</span></span> <span data-ttu-id="6334b-111">В настоящее время должно быть равным 0.</span><span class="sxs-lookup"><span data-stu-id="6334b-111">Currently should be set to 0.</span></span>  
  
## <a name="returns"></a><span data-ttu-id="6334b-112">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="6334b-112">Returns</span></span>  
 <span data-ttu-id="6334b-113">S_OK</span><span class="sxs-lookup"><span data-stu-id="6334b-113">S_OK</span></span>  
 <span data-ttu-id="6334b-114">Функция выполнена успешно.</span><span class="sxs-lookup"><span data-stu-id="6334b-114">The function succeeded.</span></span>  
  
 [<span data-ttu-id="6334b-115">LOCALDB_ERROR_NOT_INSTALLED</span><span class="sxs-lookup"><span data-stu-id="6334b-115">LOCALDB_ERROR_NOT_INSTALLED</span></span>](../express-localdb-error-messages/localdb-error-not-installed.md)  
 <span data-ttu-id="6334b-116">Компонент SQL Server Express LocalDB не установлен на компьютере.</span><span class="sxs-lookup"><span data-stu-id="6334b-116">SQL Server Express LocalDB is not installed on the computer.</span></span>  
  
 [<span data-ttu-id="6334b-117">LOCALDB_ERROR_INVALID_PARAMETER</span><span class="sxs-lookup"><span data-stu-id="6334b-117">LOCALDB_ERROR_INVALID_PARAMETER</span></span>](../express-localdb-error-messages/localdb-error-invalid-parameter.md)  
 <span data-ttu-id="6334b-118">Один или несколько указанных входных параметров недопустимы.</span><span class="sxs-lookup"><span data-stu-id="6334b-118">One or more specified input parameters are invalid.</span></span>  
  
 [<span data-ttu-id="6334b-119">LOCALDB_ERROR_INVALID_INSTANCE_NAME</span><span class="sxs-lookup"><span data-stu-id="6334b-119">LOCALDB_ERROR_INVALID_INSTANCE_NAME</span></span>](../express-localdb-error-messages/localdb-error-invalid-instance-name.md)  
 <span data-ttu-id="6334b-120">Указанное имя экземпляра недопустимо.</span><span class="sxs-lookup"><span data-stu-id="6334b-120">The specified instance name is invalid.</span></span>  
  
 [<span data-ttu-id="6334b-121">LOCALDB_ERROR_UNKNOWN_INSTANCE</span><span class="sxs-lookup"><span data-stu-id="6334b-121">LOCALDB_ERROR_UNKNOWN_INSTANCE</span></span>](../express-localdb-error-messages/localdb-error-unknown-instance.md)  
 <span data-ttu-id="6334b-122">Указанный экземпляр не существует.</span><span class="sxs-lookup"><span data-stu-id="6334b-122">The specified instance does not exist.</span></span>  
  
 [<span data-ttu-id="6334b-123">LOCALDB_ERROR_ADMIN_RIGHTS_REQUIRED</span><span class="sxs-lookup"><span data-stu-id="6334b-123">LOCALDB_ERROR_ADMIN_RIGHTS_REQUIRED</span></span>](../express-localdb-error-messages/localdb-error-admin-rights-required.md)  
 <span data-ttu-id="6334b-124">Для выполнения этой операции требуются права администратора.</span><span class="sxs-lookup"><span data-stu-id="6334b-124">Administrator privileges are required in order to execute this operation.</span></span>  
  
 [<span data-ttu-id="6334b-125">LOCALDB_ERROR_INTERNAL_ERROR</span><span class="sxs-lookup"><span data-stu-id="6334b-125">LOCALDB_ERROR_INTERNAL_ERROR</span></span>](../express-localdb-error-messages/localdb-error-internal-error.md)  
 <span data-ttu-id="6334b-126">Произошла непредвиденная ошибка.</span><span class="sxs-lookup"><span data-stu-id="6334b-126">An unexpected error occurred.</span></span> <span data-ttu-id="6334b-127">Подробные сведения см. в журнале событий.</span><span class="sxs-lookup"><span data-stu-id="6334b-127">See the event log for details.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="6334b-128">Remarks</span><span class="sxs-lookup"><span data-stu-id="6334b-128">Remarks</span></span>  
 <span data-ttu-id="6334b-129">Образец кода, использующего API LocalDB, см. в разделе [SQL Server Express LocalDB Reference](../sql-server-express-localdb-reference.md)</span><span class="sxs-lookup"><span data-stu-id="6334b-129">For a code sample that uses LocalDB API, see [SQL Server Express LocalDB Reference](../sql-server-express-localdb-reference.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6334b-130">См. также:</span><span class="sxs-lookup"><span data-stu-id="6334b-130">See Also</span></span>  
 [<span data-ttu-id="6334b-131">Заголовок и сведения о версии SQL Server Express LocalDB</span><span class="sxs-lookup"><span data-stu-id="6334b-131">SQL Server Express LocalDB Header and Version Information</span></span>](sql-server-express-localdb-header-and-version-information.md)  
  
  
