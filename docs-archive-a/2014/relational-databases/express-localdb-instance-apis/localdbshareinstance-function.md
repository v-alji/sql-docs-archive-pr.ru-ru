---
title: Функция LocalDBShareInstance | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: reference
api_name:
- LocalDBShareInstance
api_location:
- sqluserinstance.dll
topic_type:
- apiref
ms.assetid: 21eb3b9a-7d32-455b-89bb-f624198cd202
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: 238bff0b3512ceb03ead186dc001165274bd4e30
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87658714"
---
# <a name="localdbshareinstance-function"></a><span data-ttu-id="d4a52-102">Функция LocalDBShareInstance</span><span class="sxs-lookup"><span data-stu-id="d4a52-102">LocalDBShareInstance Function</span></span>
  <span data-ttu-id="d4a52-103">Разделяет указанный экземпляр SQL Server Express LocalDB с другими пользователями компьютера, используя указанное общее имя.</span><span class="sxs-lookup"><span data-stu-id="d4a52-103">Shares the specified SQL Server Express LocalDB instance with other users of the computer, using the specified shared name.</span></span>  
  
 <span data-ttu-id="d4a52-104">**Файл заголовка:** sqlncli.h</span><span class="sxs-lookup"><span data-stu-id="d4a52-104">**Header file:** sqlncli.h</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d4a52-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="d4a52-105">Syntax</span></span>  
  
```  
HRESULT LocalDBShareInstance(  
           PSID pOwnerSID,  
           PCWSTR pInstancePrivateName,  
           PCWSTR pInstanceSharedName,   
           DWORD dwFlags   
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d4a52-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="d4a52-106">Parameters</span></span>  
 <span data-ttu-id="d4a52-107">*повнерсид*</span><span class="sxs-lookup"><span data-stu-id="d4a52-107">*pOwnerSID*</span></span>  
 <span data-ttu-id="d4a52-108">[Вход] Идентификатор безопасности владельца экземпляра.</span><span class="sxs-lookup"><span data-stu-id="d4a52-108">[Input] The SID of the instance owner.</span></span>  
  
 <span data-ttu-id="d4a52-109">*пинстанцеприватенаме*</span><span class="sxs-lookup"><span data-stu-id="d4a52-109">*pInstancePrivateName*</span></span>  
 <span data-ttu-id="d4a52-110">[Вход] Частное имя разделяемого экземпляра LocalDB.</span><span class="sxs-lookup"><span data-stu-id="d4a52-110">[Input] The private name for the LocalDB instance to share.</span></span>  
  
 <span data-ttu-id="d4a52-111">*пинстанцешареднаме*</span><span class="sxs-lookup"><span data-stu-id="d4a52-111">*pInstanceSharedName*</span></span>  
 <span data-ttu-id="d4a52-112">[Вход] Общее имя разделяемого экземпляра LocalDB.</span><span class="sxs-lookup"><span data-stu-id="d4a52-112">[Input] The shared name for the LocalDB instance to share.</span></span>  
  
 <span data-ttu-id="d4a52-113">*dwFlags*</span><span class="sxs-lookup"><span data-stu-id="d4a52-113">*dwFlags*</span></span>  
 <span data-ttu-id="d4a52-114">[Вход] Зарезервировано для использования в будущем.</span><span class="sxs-lookup"><span data-stu-id="d4a52-114">[Input] Reserved for future use.</span></span> <span data-ttu-id="d4a52-115">В настоящее время должно быть равным 0.</span><span class="sxs-lookup"><span data-stu-id="d4a52-115">Currently should be set to 0.</span></span>  
  
## <a name="returns"></a><span data-ttu-id="d4a52-116">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="d4a52-116">Returns</span></span>  
 <span data-ttu-id="d4a52-117">S_OK</span><span class="sxs-lookup"><span data-stu-id="d4a52-117">S_OK</span></span>  
 <span data-ttu-id="d4a52-118">Функция выполнена успешно.</span><span class="sxs-lookup"><span data-stu-id="d4a52-118">The function succeeded.</span></span>  
  
 [<span data-ttu-id="d4a52-119">LOCALDB_ERROR_NOT_INSTALLED</span><span class="sxs-lookup"><span data-stu-id="d4a52-119">LOCALDB_ERROR_NOT_INSTALLED</span></span>](../express-localdb-error-messages/localdb-error-not-installed.md)  
 <span data-ttu-id="d4a52-120">Компонент SQL Server Express LocalDB не установлен на компьютере.</span><span class="sxs-lookup"><span data-stu-id="d4a52-120">SQL Server Express LocalDB is not installed on the computer.</span></span>  
  
 [<span data-ttu-id="d4a52-121">LOCALDB_ERROR_INVALID_PARAMETER</span><span class="sxs-lookup"><span data-stu-id="d4a52-121">LOCALDB_ERROR_INVALID_PARAMETER</span></span>](../express-localdb-error-messages/localdb-error-invalid-parameter.md)  
 <span data-ttu-id="d4a52-122">Один или несколько указанных входных параметров недопустимы.</span><span class="sxs-lookup"><span data-stu-id="d4a52-122">One or more specified input parameters are invalid.</span></span>  
  
 [<span data-ttu-id="d4a52-123">LOCALDB_ERROR_INVALID_INSTANCE_NAME</span><span class="sxs-lookup"><span data-stu-id="d4a52-123">LOCALDB_ERROR_INVALID_INSTANCE_NAME</span></span>](../express-localdb-error-messages/localdb-error-invalid-instance-name.md)  
 <span data-ttu-id="d4a52-124">Указанное имя экземпляра недопустимо.</span><span class="sxs-lookup"><span data-stu-id="d4a52-124">The specified instance name is invalid.</span></span>  
  
 [<span data-ttu-id="d4a52-125">LOCALDB_ERROR_UNKNOWN_INSTANCE</span><span class="sxs-lookup"><span data-stu-id="d4a52-125">LOCALDB_ERROR_UNKNOWN_INSTANCE</span></span>](../express-localdb-error-messages/localdb-error-unknown-instance.md)  
 <span data-ttu-id="d4a52-126">Указанный экземпляр не существует.</span><span class="sxs-lookup"><span data-stu-id="d4a52-126">The specified instance does not exist.</span></span>  
  
 [<span data-ttu-id="d4a52-127">LOCALDB_ERROR_ADMIN_RIGHTS_REQUIRED</span><span class="sxs-lookup"><span data-stu-id="d4a52-127">LOCALDB_ERROR_ADMIN_RIGHTS_REQUIRED</span></span>](../express-localdb-error-messages/localdb-error-admin-rights-required.md)  
 <span data-ttu-id="d4a52-128">Для выполнения этой операции требуются права администратора.</span><span class="sxs-lookup"><span data-stu-id="d4a52-128">Administrator privileges are required in order to execute this operation.</span></span>  
  
 [<span data-ttu-id="d4a52-129">LOCALDB_ERROR_SHARED_NAME_TAKEN</span><span class="sxs-lookup"><span data-stu-id="d4a52-129">LOCALDB_ERROR_SHARED_NAME_TAKEN</span></span>](../express-localdb-error-messages/localdb-error-shared-name-taken.md)  
 <span data-ttu-id="d4a52-130">Указанное общее имя уже занято.</span><span class="sxs-lookup"><span data-stu-id="d4a52-130">The specified shared name is already taken.</span></span>  
  
 [<span data-ttu-id="d4a52-131">LOCALDB_ERROR_INSTANCE_ALREADY_SHARED</span><span class="sxs-lookup"><span data-stu-id="d4a52-131">LOCALDB_ERROR_INSTANCE_ALREADY_SHARED</span></span>](../express-localdb-error-messages/localdb-error-instance-already-shared.md)  
 <span data-ttu-id="d4a52-132">Указанный экземпляр уже используется совместно.</span><span class="sxs-lookup"><span data-stu-id="d4a52-132">The specified instance is already shared.</span></span>  
  
 [<span data-ttu-id="d4a52-133">LOCALDB_ERROR_INTERNAL_ERROR</span><span class="sxs-lookup"><span data-stu-id="d4a52-133">LOCALDB_ERROR_INTERNAL_ERROR</span></span>](../express-localdb-error-messages/localdb-error-internal-error.md)  
 <span data-ttu-id="d4a52-134">Произошла непредвиденная ошибка.</span><span class="sxs-lookup"><span data-stu-id="d4a52-134">An unexpected error occurred.</span></span> <span data-ttu-id="d4a52-135">Подробные сведения см. в журнале событий.</span><span class="sxs-lookup"><span data-stu-id="d4a52-135">See the event log for details.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d4a52-136">Remarks</span><span class="sxs-lookup"><span data-stu-id="d4a52-136">Remarks</span></span>  
 <span data-ttu-id="d4a52-137">Образец кода, использующего API LocalDB, см. в разделе [SQL Server Express LocalDB Reference](../sql-server-express-localdb-reference.md)</span><span class="sxs-lookup"><span data-stu-id="d4a52-137">For a code sample that uses LocalDB API, see [SQL Server Express LocalDB Reference](../sql-server-express-localdb-reference.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d4a52-138">См. также:</span><span class="sxs-lookup"><span data-stu-id="d4a52-138">See Also</span></span>  
 [<span data-ttu-id="d4a52-139">Заголовок и сведения о версии SQL Server Express LocalDB</span><span class="sxs-lookup"><span data-stu-id="d4a52-139">SQL Server Express LocalDB Header and Version Information</span></span>](sql-server-express-localdb-header-and-version-information.md)  
  
  
