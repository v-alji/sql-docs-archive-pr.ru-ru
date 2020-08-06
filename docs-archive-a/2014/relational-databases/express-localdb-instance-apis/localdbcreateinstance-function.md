---
title: Функция LocalDBCreateInstance | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: reference
api_name:
- LocalDBCreateInstance
api_location:
- sqluserinstance.dll
topic_type:
- apiref
ms.assetid: 3eebb485-8a53-4a79-82a9-57b8de9f8e84
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: ff822c552176ad8c083a1c8ea6c0f2430f72972f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87666628"
---
# <a name="localdbcreateinstance-function"></a><span data-ttu-id="f3b60-102">Функция LocalDBCreateInstance</span><span class="sxs-lookup"><span data-stu-id="f3b60-102">LocalDBCreateInstance Function</span></span>
  <span data-ttu-id="f3b60-103">Создает новый экземпляр SQL Server Express LocalDB.</span><span class="sxs-lookup"><span data-stu-id="f3b60-103">Creates a new SQL Server Express LocalDB instance.</span></span>  
  
 <span data-ttu-id="f3b60-104">**Файл заголовка:** sqlncli.h</span><span class="sxs-lookup"><span data-stu-id="f3b60-104">**Header file:** sqlncli.h</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f3b60-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="f3b60-105">Syntax</span></span>  
  
```  
HRESULT LocalDBCreateInstance(  
           PCWSTR wszVersion,  
           PCWSTR pInstanceName,   
           DWORD dwFlags   
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f3b60-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="f3b60-106">Parameters</span></span>  
 <span data-ttu-id="f3b60-107">*всзверсион*</span><span class="sxs-lookup"><span data-stu-id="f3b60-107">*wszVersion*</span></span>  
 <span data-ttu-id="f3b60-108">[Вход] Версия LocalDB, например 11.0 или 11.0.1094.2.</span><span class="sxs-lookup"><span data-stu-id="f3b60-108">[Input] The LocalDB version, for example 11.0 or 11.0.1094.2.</span></span>  
  
 <span data-ttu-id="f3b60-109">*пинстанценаме*</span><span class="sxs-lookup"><span data-stu-id="f3b60-109">*pInstanceName*</span></span>  
 <span data-ttu-id="f3b60-110">[Вход] Имя создаваемого экземпляра LocalDB.</span><span class="sxs-lookup"><span data-stu-id="f3b60-110">[Input] The name for the LocalDB instance to create.</span></span>  
  
 <span data-ttu-id="f3b60-111">*dwFlags*</span><span class="sxs-lookup"><span data-stu-id="f3b60-111">*dwFlags*</span></span>  
 <span data-ttu-id="f3b60-112">[Вход] Зарезервировано для использования в будущем.</span><span class="sxs-lookup"><span data-stu-id="f3b60-112">[Input] Reserved for future use.</span></span> <span data-ttu-id="f3b60-113">В настоящее время должно быть равным 0.</span><span class="sxs-lookup"><span data-stu-id="f3b60-113">Currently should be set to 0.</span></span>  
  
## <a name="returns"></a><span data-ttu-id="f3b60-114">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="f3b60-114">Returns</span></span>  
 <span data-ttu-id="f3b60-115">S_OK</span><span class="sxs-lookup"><span data-stu-id="f3b60-115">S_OK</span></span>  
 <span data-ttu-id="f3b60-116">Функция выполнена успешно.</span><span class="sxs-lookup"><span data-stu-id="f3b60-116">The function succeeded.</span></span>  
  
 [<span data-ttu-id="f3b60-117">LOCALDB_ERROR_NOT_INSTALLED</span><span class="sxs-lookup"><span data-stu-id="f3b60-117">LOCALDB_ERROR_NOT_INSTALLED</span></span>](../express-localdb-error-messages/localdb-error-not-installed.md)  
 <span data-ttu-id="f3b60-118">Компонент SQL Server Express LocalDB не установлен на компьютере.</span><span class="sxs-lookup"><span data-stu-id="f3b60-118">SQL Server Express LocalDB is not installed on the computer.</span></span>  
  
 [<span data-ttu-id="f3b60-119">LOCALDB_ERROR_INVALID_PARAMETER</span><span class="sxs-lookup"><span data-stu-id="f3b60-119">LOCALDB_ERROR_INVALID_PARAMETER</span></span>](../express-localdb-error-messages/localdb-error-invalid-parameter.md)  
 <span data-ttu-id="f3b60-120">Один или несколько указанных входных параметров недопустимы.</span><span class="sxs-lookup"><span data-stu-id="f3b60-120">One or more specified input parameters are invalid.</span></span>  
  
 [<span data-ttu-id="f3b60-121">LOCALDB_ERROR_INVALID_INSTANCE_NAME</span><span class="sxs-lookup"><span data-stu-id="f3b60-121">LOCALDB_ERROR_INVALID_INSTANCE_NAME</span></span>](../express-localdb-error-messages/localdb-error-invalid-instance-name.md)  
 <span data-ttu-id="f3b60-122">Указанное имя экземпляра недопустимо.</span><span class="sxs-lookup"><span data-stu-id="f3b60-122">The specified instance name is invalid.</span></span>  
  
 [<span data-ttu-id="f3b60-123">LOCALDB_ERROR_INSTANCE_FOLDER_PATH_TOO_LONG</span><span class="sxs-lookup"><span data-stu-id="f3b60-123">LOCALDB_ERROR_INSTANCE_FOLDER_PATH_TOO_LONG</span></span>](../express-localdb-error-messages/localdb-error-instance-folder-path-too-long.md)  
 <span data-ttu-id="f3b60-124">Длина пути к месту хранения экземпляра больше MAX_PATH.</span><span class="sxs-lookup"><span data-stu-id="f3b60-124">The path where the instance should be stored is longer than MAX_PATH.</span></span>  
  
 [<span data-ttu-id="f3b60-125">LOCALDB_ERROR_INSTANCE_EXISTS_WITH_LOWER_VERSION</span><span class="sxs-lookup"><span data-stu-id="f3b60-125">LOCALDB_ERROR_INSTANCE_EXISTS_WITH_LOWER_VERSION</span></span>](../express-localdb-error-messages/localdb-error-instance-exists-with-lower-version.md)  
 <span data-ttu-id="f3b60-126">Указанный экземпляр уже существует, но его версия ниже запрошенной.</span><span class="sxs-lookup"><span data-stu-id="f3b60-126">The specified instance already exists but its version is lower than requested.</span></span>  
  
 [<span data-ttu-id="f3b60-127">LOCALDB_ERROR_UNKNOWN_VERSION</span><span class="sxs-lookup"><span data-stu-id="f3b60-127">LOCALDB_ERROR_UNKNOWN_VERSION</span></span>](../express-localdb-error-messages/localdb-error-unknown-version.md)  
 <span data-ttu-id="f3b60-128">Указанная версия недоступна.</span><span class="sxs-lookup"><span data-stu-id="f3b60-128">The specified version is not available.</span></span>  
  
 [<span data-ttu-id="f3b60-129">LOCALDB_ERROR_VERSION_REQUESTED_NOT_INSTALLED</span><span class="sxs-lookup"><span data-stu-id="f3b60-129">LOCALDB_ERROR_VERSION_REQUESTED_NOT_INSTALLED</span></span>](../express-localdb-error-messages/localdb-error-version-requested-not-installed.md)  
 <span data-ttu-id="f3b60-130">Указанный уровень обновления не установлен.</span><span class="sxs-lookup"><span data-stu-id="f3b60-130">The specified patch level is not installed.</span></span>  
  
 [<span data-ttu-id="f3b60-131">LOCALDB_ERROR_CANNOT_CREATE_INSTANCE_FOLDER</span><span class="sxs-lookup"><span data-stu-id="f3b60-131">LOCALDB_ERROR_CANNOT_CREATE_INSTANCE_FOLDER</span></span>](../express-localdb-error-messages/localdb-error-cannot-create-instance-folder.md)  
 <span data-ttu-id="f3b60-132">Невозможно создать папку в %userprofile%.</span><span class="sxs-lookup"><span data-stu-id="f3b60-132">A folder cannot be created under %userprofile%.</span></span>  
  
 [<span data-ttu-id="f3b60-133">LOCALDB_ERROR_CANNOT_GET_USER_PROFILE_FOLDER</span><span class="sxs-lookup"><span data-stu-id="f3b60-133">LOCALDB_ERROR_CANNOT_GET_USER_PROFILE_FOLDER</span></span>](../express-localdb-error-messages/localdb-error-cannot-get-user-profile-folder.md)  
 <span data-ttu-id="f3b60-134">Не удалось получить папку профиля пользователя.</span><span class="sxs-lookup"><span data-stu-id="f3b60-134">A user profile folder cannot be retrieved.</span></span>  
  
 [<span data-ttu-id="f3b60-135">LOCALDB_ERROR_CANNOT_ACCESS_INSTANCE_FOLDER</span><span class="sxs-lookup"><span data-stu-id="f3b60-135">LOCALDB_ERROR_CANNOT_ACCESS_INSTANCE_FOLDER</span></span>](../express-localdb-error-messages/localdb-error-cannot-access-instance-folder.md)  
 <span data-ttu-id="f3b60-136">Не удалось получить доступ к папке экземпляра.</span><span class="sxs-lookup"><span data-stu-id="f3b60-136">An instance folder cannot be accessed.</span></span>  
  
 [<span data-ttu-id="f3b60-137">LOCALDB_ERROR_CANNOT_ACCESS_INSTANCE_REGISTRY</span><span class="sxs-lookup"><span data-stu-id="f3b60-137">LOCALDB_ERROR_CANNOT_ACCESS_INSTANCE_REGISTRY</span></span>](../express-localdb-error-messages/localdb-error-cannot-access-instance-registry.md)  
 <span data-ttu-id="f3b60-138">Не удалось получить доступ к реестру экземпляра.</span><span class="sxs-lookup"><span data-stu-id="f3b60-138">An instance registry cannot be accessed.</span></span>  
  
 [<span data-ttu-id="f3b60-139">LOCALDB_ERROR_CANNOT_MODIFY_INSTANCE_REGISTRY</span><span class="sxs-lookup"><span data-stu-id="f3b60-139">LOCALDB_ERROR_CANNOT_MODIFY_INSTANCE_REGISTRY</span></span>](../express-localdb-error-messages/localdb-error-cannot-modify-instance-registry.md)  
 <span data-ttu-id="f3b60-140">Невозможно изменить реестр экземпляра.</span><span class="sxs-lookup"><span data-stu-id="f3b60-140">An instance registry cannot be modified.</span></span>  
  
 [<span data-ttu-id="f3b60-141">LOCALDB_ERROR_SQL_SERVER_STARTUP_FAILED</span><span class="sxs-lookup"><span data-stu-id="f3b60-141">LOCALDB_ERROR_SQL_SERVER_STARTUP_FAILED</span></span>](../express-localdb-error-messages/localdb-error-sql-server-startup-failed.md)  
 <span data-ttu-id="f3b60-142">Был запущен процесс SQL Server, но запуск SQL Server завершился с ошибкой.</span><span class="sxs-lookup"><span data-stu-id="f3b60-142">A SQL Server process is started but SQL Server startup failed.</span></span>  
  
 [<span data-ttu-id="f3b60-143">LOCALDB_ERROR_INSTANCE_CONFIGURATION_CORRUPT</span><span class="sxs-lookup"><span data-stu-id="f3b60-143">LOCALDB_ERROR_INSTANCE_CONFIGURATION_CORRUPT</span></span>](../express-localdb-error-messages/localdb-error-instance-configuration-corrupt.md)  
 <span data-ttu-id="f3b60-144">Конфигурация экземпляра повреждена.</span><span class="sxs-lookup"><span data-stu-id="f3b60-144">An instance configuration is corrupted.</span></span>  
  
 [<span data-ttu-id="f3b60-145">LOCALDB_ERROR_INTERNAL_ERROR</span><span class="sxs-lookup"><span data-stu-id="f3b60-145">LOCALDB_ERROR_INTERNAL_ERROR</span></span>](../express-localdb-error-messages/localdb-error-internal-error.md)  
 <span data-ttu-id="f3b60-146">Произошла непредвиденная ошибка.</span><span class="sxs-lookup"><span data-stu-id="f3b60-146">An unexpected error occurred.</span></span> <span data-ttu-id="f3b60-147">Подробные сведения см. в журнале событий.</span><span class="sxs-lookup"><span data-stu-id="f3b60-147">See the event log for details.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f3b60-148">Remarks</span><span class="sxs-lookup"><span data-stu-id="f3b60-148">Remarks</span></span>  
 <span data-ttu-id="f3b60-149">Если существует полностью функциональный экземпляр LocalDB с указанным именем и его версия равна или выше запрошенной, возвращается результат S_OK.</span><span class="sxs-lookup"><span data-stu-id="f3b60-149">If a fully functional LocalDB instance with the specified name already exists and its version is equal to or higher than requested, the result is S_OK.</span></span>  
  
 <span data-ttu-id="f3b60-150">В случае, если существующий экземпляр поврежден, последующие вызовы метода API `LocalDBCreateInstance` завершатся с ошибкой.</span><span class="sxs-lookup"><span data-stu-id="f3b60-150">In cases when an existing instance becomes corrupted, subsequent calls to the `LocalDBCreateInstance` API method will fail.</span></span> <span data-ttu-id="f3b60-151">Поврежденный экземпляр необходимо исправить вручную или явно удалить, чтобы его можно было использовать снова.</span><span class="sxs-lookup"><span data-stu-id="f3b60-151">Corrupted instances must be fixed manually or explicitly deleted before they can be used again.</span></span>  
  
 <span data-ttu-id="f3b60-152">Образец кода, использующего API LocalDB, см. в разделе [SQL Server Express LocalDB Reference](../sql-server-express-localdb-reference.md)</span><span class="sxs-lookup"><span data-stu-id="f3b60-152">For a code sample that uses LocalDB API, see [SQL Server Express LocalDB Reference](../sql-server-express-localdb-reference.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f3b60-153">См. также:</span><span class="sxs-lookup"><span data-stu-id="f3b60-153">See Also</span></span>  
 [<span data-ttu-id="f3b60-154">Заголовок и сведения о версии SQL Server Express LocalDB</span><span class="sxs-lookup"><span data-stu-id="f3b60-154">SQL Server Express LocalDB Header and Version Information</span></span>](sql-server-express-localdb-header-and-version-information.md)  
  
  
