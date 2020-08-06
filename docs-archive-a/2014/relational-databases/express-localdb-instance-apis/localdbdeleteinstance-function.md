---
title: Функция Локалдбделетеинстанце | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: reference
api_name:
- LocalDBDeleteInstance
api_location:
- sqluserinstance.dll
topic_type:
- apiref
ms.assetid: 37cb2a7e-672a-4223-b6f3-a94d7b8d58cd
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: 8d4c873e045c5effed476ca9d147270d159ec3b2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87666623"
---
# <a name="localdbdeleteinstance-function"></a><span data-ttu-id="975f7-102">Функция LocalDBDeleteInstance</span><span class="sxs-lookup"><span data-stu-id="975f7-102">LocalDBDeleteInstance Function</span></span>
  <span data-ttu-id="975f7-103">Удаляет экземпляр SQL Server Express LocalDB.</span><span class="sxs-lookup"><span data-stu-id="975f7-103">Removes the specified SQL Server Express LocalDB instance.</span></span>  
  
 <span data-ttu-id="975f7-104">**Файл заголовка:** sqlncli.h</span><span class="sxs-lookup"><span data-stu-id="975f7-104">**Header file:** sqlncli.h</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="975f7-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="975f7-105">Syntax</span></span>  
  
```  
HRESULT LocalDBDeleteInstance(  
           PCWSTR pInstanceName,  
           DWORD dwFlags   
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="975f7-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="975f7-106">Parameters</span></span>  
 <span data-ttu-id="975f7-107">*пинстанценаме*</span><span class="sxs-lookup"><span data-stu-id="975f7-107">*pInstanceName*</span></span>  
 <span data-ttu-id="975f7-108">[Вход] Имя удаляемого экземпляра LocalDB.</span><span class="sxs-lookup"><span data-stu-id="975f7-108">[Input] The name of the LocalDB instance to remove.</span></span>  
  
 <span data-ttu-id="975f7-109">*dwFlags*</span><span class="sxs-lookup"><span data-stu-id="975f7-109">*dwFlags*</span></span>  
 <span data-ttu-id="975f7-110">[Вход] Зарезервировано для использования в будущем.</span><span class="sxs-lookup"><span data-stu-id="975f7-110">[Input] Reserved for future use.</span></span> <span data-ttu-id="975f7-111">В настоящее время должно быть равным 0.</span><span class="sxs-lookup"><span data-stu-id="975f7-111">Currently should be set to 0.</span></span>  
  
## <a name="returns"></a><span data-ttu-id="975f7-112">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="975f7-112">Returns</span></span>  
 <span data-ttu-id="975f7-113">S_OK</span><span class="sxs-lookup"><span data-stu-id="975f7-113">S_OK</span></span>  
 <span data-ttu-id="975f7-114">Функция выполнена успешно.</span><span class="sxs-lookup"><span data-stu-id="975f7-114">The function succeeded.</span></span>  
  
 [<span data-ttu-id="975f7-115">LOCALDB_ERROR_NOT_INSTALLED</span><span class="sxs-lookup"><span data-stu-id="975f7-115">LOCALDB_ERROR_NOT_INSTALLED</span></span>](../express-localdb-error-messages/localdb-error-not-installed.md)  
 <span data-ttu-id="975f7-116">Компонент SQL Server Express LocalDB не установлен на компьютере.</span><span class="sxs-lookup"><span data-stu-id="975f7-116">SQL Server Express LocalDB is not installed on the computer.</span></span>  
  
 [<span data-ttu-id="975f7-117">LOCALDB_ERROR_INVALID_PARAMETER</span><span class="sxs-lookup"><span data-stu-id="975f7-117">LOCALDB_ERROR_INVALID_PARAMETER</span></span>](../express-localdb-error-messages/localdb-error-invalid-parameter.md)  
 <span data-ttu-id="975f7-118">Один или несколько указанных входных параметров недопустимы.</span><span class="sxs-lookup"><span data-stu-id="975f7-118">One or more specified input parameters are invalid.</span></span>  
  
 [<span data-ttu-id="975f7-119">LOCALDB_ERROR_INVALID_INSTANCE_NAME</span><span class="sxs-lookup"><span data-stu-id="975f7-119">LOCALDB_ERROR_INVALID_INSTANCE_NAME</span></span>](../express-localdb-error-messages/localdb-error-invalid-instance-name.md)  
 <span data-ttu-id="975f7-120">Указанное имя экземпляра недопустимо.</span><span class="sxs-lookup"><span data-stu-id="975f7-120">The specified instance name is invalid.</span></span>  
  
 [<span data-ttu-id="975f7-121">LOCALDB_ERROR_UNKNOWN_INSTANCE</span><span class="sxs-lookup"><span data-stu-id="975f7-121">LOCALDB_ERROR_UNKNOWN_INSTANCE</span></span>](../express-localdb-error-messages/localdb-error-unknown-instance.md)  
 <span data-ttu-id="975f7-122">Указанный экземпляр не существует.</span><span class="sxs-lookup"><span data-stu-id="975f7-122">The specified instance does not exist.</span></span>  
  
 [<span data-ttu-id="975f7-123">LOCALDB_ERROR_INSTANCE_BUSY</span><span class="sxs-lookup"><span data-stu-id="975f7-123">LOCALDB_ERROR_INSTANCE_BUSY</span></span>](../express-localdb-error-messages/localdb-error-instance-busy.md)  
 <span data-ttu-id="975f7-124">Указанный экземпляр выполняется.</span><span class="sxs-lookup"><span data-stu-id="975f7-124">The specified instance is running.</span></span>  
  
 [<span data-ttu-id="975f7-125">LOCALDB_ERROR_WAIT_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="975f7-125">LOCALDB_ERROR_WAIT_TIMEOUT</span></span>](../express-localdb-error-messages/localdb-error-wait-timeout.md)  
 <span data-ttu-id="975f7-126">При попытке получения блокировок синхронизации истекло время ожидания.</span><span class="sxs-lookup"><span data-stu-id="975f7-126">A time-out occurred while trying to acquire synchronization locks.</span></span>  
  
 [<span data-ttu-id="975f7-127">LOCALDB_ERROR_INSTANCE_FOLDER_PATH_TOO_LONG</span><span class="sxs-lookup"><span data-stu-id="975f7-127">LOCALDB_ERROR_INSTANCE_FOLDER_PATH_TOO_LONG</span></span>](../express-localdb-error-messages/localdb-error-instance-folder-path-too-long.md)  
 <span data-ttu-id="975f7-128">Длина пути к месту хранения экземпляра больше MAX_PATH.</span><span class="sxs-lookup"><span data-stu-id="975f7-128">The path where the instance should be stored is longer than MAX_PATH.</span></span>  
  
 [<span data-ttu-id="975f7-129">LOCALDB_ERROR_CANNOT_GET_USER_PROFILE_FOLDER</span><span class="sxs-lookup"><span data-stu-id="975f7-129">LOCALDB_ERROR_CANNOT_GET_USER_PROFILE_FOLDER</span></span>](../express-localdb-error-messages/localdb-error-cannot-get-user-profile-folder.md)  
 <span data-ttu-id="975f7-130">Не удалось получить папку профиля пользователя.</span><span class="sxs-lookup"><span data-stu-id="975f7-130">A user profile folder cannot be retrieved.</span></span>  
  
 [<span data-ttu-id="975f7-131">LOCALDB_ERROR_CANNOT_ACCESS_INSTANCE_FOLDER</span><span class="sxs-lookup"><span data-stu-id="975f7-131">LOCALDB_ERROR_CANNOT_ACCESS_INSTANCE_FOLDER</span></span>](../express-localdb-error-messages/localdb-error-cannot-access-instance-folder.md)  
 <span data-ttu-id="975f7-132">Не удалось получить доступ к папке экземпляра.</span><span class="sxs-lookup"><span data-stu-id="975f7-132">An instance folder cannot be accessed.</span></span>  
  
 [<span data-ttu-id="975f7-133">LOCALDB_ERROR_CANNOT_ACCESS_INSTANCE_REGISTRY</span><span class="sxs-lookup"><span data-stu-id="975f7-133">LOCALDB_ERROR_CANNOT_ACCESS_INSTANCE_REGISTRY</span></span>](../express-localdb-error-messages/localdb-error-cannot-access-instance-registry.md)  
 <span data-ttu-id="975f7-134">Не удалось получить доступ к реестру экземпляра.</span><span class="sxs-lookup"><span data-stu-id="975f7-134">An instance registry cannot be accessed.</span></span>  
  
 [<span data-ttu-id="975f7-135">LOCALDB_ERROR_CANNOT_MODIFY_INSTANCE_REGISTRY</span><span class="sxs-lookup"><span data-stu-id="975f7-135">LOCALDB_ERROR_CANNOT_MODIFY_INSTANCE_REGISTRY</span></span>](../express-localdb-error-messages/localdb-error-cannot-modify-instance-registry.md)  
 <span data-ttu-id="975f7-136">Невозможно изменить реестр экземпляра.</span><span class="sxs-lookup"><span data-stu-id="975f7-136">An instance registry cannot be modified.</span></span>  
  
 [<span data-ttu-id="975f7-137">LOCALDB_ERROR_INSTANCE_CONFIGURATION_CORRUPT</span><span class="sxs-lookup"><span data-stu-id="975f7-137">LOCALDB_ERROR_INSTANCE_CONFIGURATION_CORRUPT</span></span>](../express-localdb-error-messages/localdb-error-instance-configuration-corrupt.md)  
 <span data-ttu-id="975f7-138">Конфигурация экземпляра повреждена.</span><span class="sxs-lookup"><span data-stu-id="975f7-138">An instance configuration is corrupted.</span></span>  
  
 [<span data-ttu-id="975f7-139">LOCALDB_ERROR_CALLER_IS_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="975f7-139">LOCALDB_ERROR_CALLER_IS_NOT_OWNER</span></span>](../express-localdb-error-messages/localdb-error-caller-is-not-owner.md)  
 <span data-ttu-id="975f7-140">Вызывающий API не является владельцем экземпляра локальной базы данных.</span><span class="sxs-lookup"><span data-stu-id="975f7-140">API caller is not Local Database instance owner.</span></span>  
  
 [<span data-ttu-id="975f7-141">LOCALDB_ERROR_INTERNAL_ERROR</span><span class="sxs-lookup"><span data-stu-id="975f7-141">LOCALDB_ERROR_INTERNAL_ERROR</span></span>](../express-localdb-error-messages/localdb-error-internal-error.md)  
 <span data-ttu-id="975f7-142">Произошла непредвиденная ошибка.</span><span class="sxs-lookup"><span data-stu-id="975f7-142">An unexpected error occurred.</span></span> <span data-ttu-id="975f7-143">Подробные сведения см. в журнале событий.</span><span class="sxs-lookup"><span data-stu-id="975f7-143">See the event log for details.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="975f7-144">Remarks</span><span class="sxs-lookup"><span data-stu-id="975f7-144">Remarks</span></span>  
 <span data-ttu-id="975f7-145">Образец кода, использующего API LocalDB, см. в разделе [SQL Server Express LocalDB Reference](../sql-server-express-localdb-reference.md)</span><span class="sxs-lookup"><span data-stu-id="975f7-145">For a code sample that uses LocalDB API, see [SQL Server Express LocalDB Reference](../sql-server-express-localdb-reference.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="975f7-146">См. также:</span><span class="sxs-lookup"><span data-stu-id="975f7-146">See Also</span></span>  
 [<span data-ttu-id="975f7-147">Заголовок и сведения о версии SQL Server Express LocalDB</span><span class="sxs-lookup"><span data-stu-id="975f7-147">SQL Server Express LocalDB Header and Version Information</span></span>](sql-server-express-localdb-header-and-version-information.md)  
  
  
