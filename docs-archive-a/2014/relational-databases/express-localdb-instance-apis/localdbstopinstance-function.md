---
title: Функция Локалдбстопинстанце | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: reference
api_name:
- LocalDBStopInstance
api_location:
- sqluserinstance.dll
topic_type:
- apiref
ms.assetid: 4bd73187-0aac-4f03-ac54-2b78e41917e5
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: 48b014e65e0a02a5f866e5301b12dae3cd255b95
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87728254"
---
# <a name="localdbstopinstance-function"></a><span data-ttu-id="c4845-102">Функция LocalDBStopInstance</span><span class="sxs-lookup"><span data-stu-id="c4845-102">LocalDBStopInstance Function</span></span>
  <span data-ttu-id="c4845-103">Останавливает указанный запущенный экземпляр SQL Server Express LocalDB.</span><span class="sxs-lookup"><span data-stu-id="c4845-103">Stops the specified SQL Server Express LocalDB instance from running.</span></span>  
  
 <span data-ttu-id="c4845-104">**Файл заголовка:** sqlncli.h</span><span class="sxs-lookup"><span data-stu-id="c4845-104">**Header file:** sqlncli.h</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c4845-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="c4845-105">Syntax</span></span>  
  
```  
HRESULT LocalDBStopInstance(  
           PCWSTR pInstanceName,  
           DWORD dwFlags,   
           ULONG ulTimeout   
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c4845-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="c4845-106">Parameters</span></span>  
 <span data-ttu-id="c4845-107">*пинстанценаме*</span><span class="sxs-lookup"><span data-stu-id="c4845-107">*pInstanceName*</span></span>  
 <span data-ttu-id="c4845-108">[Вход] Имя останавливаемого экземпляра LocalDB.</span><span class="sxs-lookup"><span data-stu-id="c4845-108">[Input] The name of the LocalDB instance to stop.</span></span>  
  
 <span data-ttu-id="c4845-109">*dwFlags*</span><span class="sxs-lookup"><span data-stu-id="c4845-109">*dwFlags*</span></span>  
 <span data-ttu-id="c4845-110">[Вход] Значение или сочетание значений флагов, задающее способ остановки экземпляра.</span><span class="sxs-lookup"><span data-stu-id="c4845-110">[Input] One or a combination of the flag values specifying the way to stop the instance.</span></span>  
  
 <span data-ttu-id="c4845-111">Доступные флаги:</span><span class="sxs-lookup"><span data-stu-id="c4845-111">Available flags:</span></span>  
  
 <span data-ttu-id="c4845-112">LOCALDB_SHUTDOWN_KILL_PROCESS</span><span class="sxs-lookup"><span data-stu-id="c4845-112">LOCALDB_SHUTDOWN_KILL_PROCESS</span></span>  
 <span data-ttu-id="c4845-113">Завершает работу немедленно с помощью команды уничтожения процесса операционной системы.</span><span class="sxs-lookup"><span data-stu-id="c4845-113">Shut down immediately using the kill process operating system command.</span></span>  
  
 <span data-ttu-id="c4845-114">LOCALDB_SHUTDOWN_WITH_NOWAIT</span><span class="sxs-lookup"><span data-stu-id="c4845-114">LOCALDB_SHUTDOWN_WITH_NOWAIT</span></span>  
 <span data-ttu-id="c4845-115">Завершает работу с использованием параметра WITH NOWAIT команды Transact-SQL.</span><span class="sxs-lookup"><span data-stu-id="c4845-115">Shut down using the WITH NOWAIT option Transact-SQL command.</span></span>  
  
 <span data-ttu-id="c4845-116">Если ни один из флагов не установлен, работа экземпляра LocalDB завершается с помощью команды Transact-SQL SHUTDOWN.</span><span class="sxs-lookup"><span data-stu-id="c4845-116">If none of the flags is set, the LocalDB instance will be shut down using the SHUTDOWN Transact-SQL command.</span></span> <span data-ttu-id="c4845-117">Если установлены оба флага, приоритет имеет флаг LOCALDB_SHUTDOWN_KILL_PROCESS.</span><span class="sxs-lookup"><span data-stu-id="c4845-117">If both flags are set, the LOCALDB_SHUTDOWN_KILL_PROCESS flag takes precedence.</span></span>  
  
 <span data-ttu-id="c4845-118">*ултимеаут*</span><span class="sxs-lookup"><span data-stu-id="c4845-118">*ulTimeout*</span></span>  
 <span data-ttu-id="c4845-119">[Вход] Время ожидания выполнения операции в секундах.</span><span class="sxs-lookup"><span data-stu-id="c4845-119">[Input] The time in seconds to wait for this operation to complete.</span></span> <span data-ttu-id="c4845-120">Если это значение равно 0, функция немедленно возвращает управление, не ожидая остановки локального экземпляра LocalDB.</span><span class="sxs-lookup"><span data-stu-id="c4845-120">If this value is 0, this function will return immediately without waiting for the LocalDB instance to stop.</span></span>  
  
## <a name="returns"></a><span data-ttu-id="c4845-121">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="c4845-121">Returns</span></span>  
 <span data-ttu-id="c4845-122">S_OK</span><span class="sxs-lookup"><span data-stu-id="c4845-122">S_OK</span></span>  
 <span data-ttu-id="c4845-123">Функция выполнена успешно.</span><span class="sxs-lookup"><span data-stu-id="c4845-123">The function succeeded.</span></span>  
  
 [<span data-ttu-id="c4845-124">LOCALDB_ERROR_NOT_INSTALLED</span><span class="sxs-lookup"><span data-stu-id="c4845-124">LOCALDB_ERROR_NOT_INSTALLED</span></span>](../express-localdb-error-messages/localdb-error-not-installed.md)  
 <span data-ttu-id="c4845-125">Компонент SQL Server Express LocalDB не установлен на компьютере.</span><span class="sxs-lookup"><span data-stu-id="c4845-125">SQL Server Express LocalDB is not installed on the computer.</span></span>  
  
 [<span data-ttu-id="c4845-126">LOCALDB_ERROR_INVALID_PARAMETER</span><span class="sxs-lookup"><span data-stu-id="c4845-126">LOCALDB_ERROR_INVALID_PARAMETER</span></span>](../express-localdb-error-messages/localdb-error-invalid-parameter.md)  
 <span data-ttu-id="c4845-127">Один или несколько указанных входных параметров недопустимы.</span><span class="sxs-lookup"><span data-stu-id="c4845-127">One or more specified input parameters are invalid.</span></span>  
  
 [<span data-ttu-id="c4845-128">LOCALDB_ERROR_INVALID_INSTANCE_NAME</span><span class="sxs-lookup"><span data-stu-id="c4845-128">LOCALDB_ERROR_INVALID_INSTANCE_NAME</span></span>](../express-localdb-error-messages/localdb-error-invalid-instance-name.md)  
 <span data-ttu-id="c4845-129">Указанное имя экземпляра недопустимо.</span><span class="sxs-lookup"><span data-stu-id="c4845-129">The specified instance name is invalid.</span></span>  
  
 [<span data-ttu-id="c4845-130">LOCALDB_ERROR_UNKNOWN_INSTANCE</span><span class="sxs-lookup"><span data-stu-id="c4845-130">LOCALDB_ERROR_UNKNOWN_INSTANCE</span></span>](../express-localdb-error-messages/localdb-error-unknown-instance.md)  
 <span data-ttu-id="c4845-131">Экземпляр не существует.</span><span class="sxs-lookup"><span data-stu-id="c4845-131">The instance does not exist.</span></span>  
  
 [<span data-ttu-id="c4845-132">LOCALDB_ERROR_WAIT_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="c4845-132">LOCALDB_ERROR_WAIT_TIMEOUT</span></span>](../express-localdb-error-messages/localdb-error-wait-timeout.md)  
 <span data-ttu-id="c4845-133">При попытке получения блокировок синхронизации истекло время ожидания.</span><span class="sxs-lookup"><span data-stu-id="c4845-133">A time-out occurred while trying to acquire the synchronization locks.</span></span>  
  
 [<span data-ttu-id="c4845-134">LOCALDB_ERROR_INSTANCE_STOP_FAILED</span><span class="sxs-lookup"><span data-stu-id="c4845-134">LOCALDB_ERROR_INSTANCE_STOP_FAILED</span></span>](../express-localdb-error-messages/localdb-error-instance-stop-failed.md)  
 <span data-ttu-id="c4845-135">Операцию остановки не удалось завершить в течение заданного времени.</span><span class="sxs-lookup"><span data-stu-id="c4845-135">The stop operation failed to complete within the given time.</span></span>  
  
 [<span data-ttu-id="c4845-136">LOCALDB_ERROR_INSTANCE_FOLDER_PATH_TOO_LONG</span><span class="sxs-lookup"><span data-stu-id="c4845-136">LOCALDB_ERROR_INSTANCE_FOLDER_PATH_TOO_LONG</span></span>](../express-localdb-error-messages/localdb-error-instance-folder-path-too-long.md)  
 <span data-ttu-id="c4845-137">Длина пути к месту хранения экземпляра больше MAX_PATH.</span><span class="sxs-lookup"><span data-stu-id="c4845-137">The path where the instance should be stored is longer than MAX_PATH.</span></span>  
  
 [<span data-ttu-id="c4845-138">LOCALDB_ERROR_CANNOT_GET_USER_PROFILE_FOLDER</span><span class="sxs-lookup"><span data-stu-id="c4845-138">LOCALDB_ERROR_CANNOT_GET_USER_PROFILE_FOLDER</span></span>](../express-localdb-error-messages/localdb-error-cannot-get-user-profile-folder.md)  
 <span data-ttu-id="c4845-139">Не удалось получить папку профиля пользователя.</span><span class="sxs-lookup"><span data-stu-id="c4845-139">A user profile folder cannot be retrieved.</span></span>  
  
 [<span data-ttu-id="c4845-140">LOCALDB_ERROR_CANNOT_ACCESS_INSTANCE_FOLDER</span><span class="sxs-lookup"><span data-stu-id="c4845-140">LOCALDB_ERROR_CANNOT_ACCESS_INSTANCE_FOLDER</span></span>](../express-localdb-error-messages/localdb-error-cannot-access-instance-folder.md)  
 <span data-ttu-id="c4845-141">Не удалось получить доступ к папке экземпляра.</span><span class="sxs-lookup"><span data-stu-id="c4845-141">An instance folder cannot be accessed.</span></span>  
  
 [<span data-ttu-id="c4845-142">LOCALDB_ERROR_CANNOT_ACCESS_INSTANCE_REGISTRY</span><span class="sxs-lookup"><span data-stu-id="c4845-142">LOCALDB_ERROR_CANNOT_ACCESS_INSTANCE_REGISTRY</span></span>](../express-localdb-error-messages/localdb-error-cannot-access-instance-registry.md)  
 <span data-ttu-id="c4845-143">Не удалось получить доступ к реестру экземпляра.</span><span class="sxs-lookup"><span data-stu-id="c4845-143">An instance registry cannot be accessed.</span></span>  
  
 [<span data-ttu-id="c4845-144">LOCALDB_ERROR_INSTANCE_CONFIGURATION_CORRUPT</span><span class="sxs-lookup"><span data-stu-id="c4845-144">LOCALDB_ERROR_INSTANCE_CONFIGURATION_CORRUPT</span></span>](../express-localdb-error-messages/localdb-error-instance-configuration-corrupt.md)  
 <span data-ttu-id="c4845-145">Конфигурация экземпляра повреждена.</span><span class="sxs-lookup"><span data-stu-id="c4845-145">An instance configuration is corrupted.</span></span>  
  
 [<span data-ttu-id="c4845-146">LOCALDB_ERROR_CALLER_IS_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="c4845-146">LOCALDB_ERROR_CALLER_IS_NOT_OWNER</span></span>](../express-localdb-error-messages/localdb-error-caller-is-not-owner.md)  
 <span data-ttu-id="c4845-147">Вызывающий API не является владельцем экземпляра LocalDB.</span><span class="sxs-lookup"><span data-stu-id="c4845-147">API caller is not LocalDB instance owner.</span></span>  
  
 [<span data-ttu-id="c4845-148">LOCALDB_ERROR_INTERNAL_ERROR</span><span class="sxs-lookup"><span data-stu-id="c4845-148">LOCALDB_ERROR_INTERNAL_ERROR</span></span>](../express-localdb-error-messages/localdb-error-internal-error.md)  
 <span data-ttu-id="c4845-149">Произошла непредвиденная ошибка.</span><span class="sxs-lookup"><span data-stu-id="c4845-149">An unexpected error occurred.</span></span> <span data-ttu-id="c4845-150">Подробные сведения см. в журнале событий.</span><span class="sxs-lookup"><span data-stu-id="c4845-150">See the event log for details.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c4845-151">Remarks</span><span class="sxs-lookup"><span data-stu-id="c4845-151">Remarks</span></span>  
 <span data-ttu-id="c4845-152">Образец кода, использующего API LocalDB, см. в разделе [SQL Server Express LocalDB Reference](../sql-server-express-localdb-reference.md)</span><span class="sxs-lookup"><span data-stu-id="c4845-152">For a code sample that uses LocalDB API, see [SQL Server Express LocalDB Reference](../sql-server-express-localdb-reference.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c4845-153">См. также:</span><span class="sxs-lookup"><span data-stu-id="c4845-153">See Also</span></span>  
 [<span data-ttu-id="c4845-154">Заголовок и сведения о версии SQL Server Express LocalDB</span><span class="sxs-lookup"><span data-stu-id="c4845-154">SQL Server Express LocalDB Header and Version Information</span></span>](sql-server-express-localdb-header-and-version-information.md)  
  
  
