---
title: Функция LocalDBStartInstance | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: reference
api_name:
- LocalDBStartInstance
api_location:
- sqluserinstance.dll
topic_type:
- apiref
ms.assetid: cb325f5d-10ee-4a56-ba28-db0074ab3926
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: 748bc373e8b0dbad0a91247e068d21b67f2dbc1a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87668343"
---
# <a name="localdbstartinstance-function"></a><span data-ttu-id="76fb5-102">Функция LocalDBStartInstance</span><span class="sxs-lookup"><span data-stu-id="76fb5-102">LocalDBStartInstance Function</span></span>
  <span data-ttu-id="76fb5-103">Запускает экземпляр SQL Server Express LocalDB.</span><span class="sxs-lookup"><span data-stu-id="76fb5-103">Starts the specified SQL Server Express LocalDB instance.</span></span>  
  
 <span data-ttu-id="76fb5-104">**Файл заголовка:** sqlncli.h</span><span class="sxs-lookup"><span data-stu-id="76fb5-104">**Header file:** sqlncli.h</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="76fb5-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="76fb5-105">Syntax</span></span>  
  
```  
HRESULT LocalDBStartInstance(  
           PCWSTR pInstanceName,  
           DWORD dwFlags,   
           LPWSTR wszSqlConnection,   
           LPDWORD lpcchSqlConnection   
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="76fb5-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="76fb5-106">Parameters</span></span>  
 <span data-ttu-id="76fb5-107">*пинстанценаме*</span><span class="sxs-lookup"><span data-stu-id="76fb5-107">*pInstanceName*</span></span>  
 <span data-ttu-id="76fb5-108">[Вход] Имя запускаемого экземпляра LocalDB.</span><span class="sxs-lookup"><span data-stu-id="76fb5-108">[Input] The name of the LocalDB instance to start.</span></span>  
  
 <span data-ttu-id="76fb5-109">*dwFlags*</span><span class="sxs-lookup"><span data-stu-id="76fb5-109">*dwFlags*</span></span>  
 <span data-ttu-id="76fb5-110">[Вход] Зарезервировано для использования в будущем.</span><span class="sxs-lookup"><span data-stu-id="76fb5-110">[Input] Reserved for future use.</span></span> <span data-ttu-id="76fb5-111">В настоящее время должно быть равным 0.</span><span class="sxs-lookup"><span data-stu-id="76fb5-111">Currently should be set to 0.</span></span>  
  
 <span data-ttu-id="76fb5-112">*wszSqlConnection*</span><span class="sxs-lookup"><span data-stu-id="76fb5-112">*wszSqlConnection*</span></span>  
 <span data-ttu-id="76fb5-113">[Выход] Буфер для хранения строки подключения к экземпляру LocalDB.</span><span class="sxs-lookup"><span data-stu-id="76fb5-113">[Output] The buffer to store the connection string to the LocalDB instance.</span></span>  
  
 <span data-ttu-id="76fb5-114">*lpcchSqlConnection*</span><span class="sxs-lookup"><span data-stu-id="76fb5-114">*lpcchSqlConnection*</span></span>  
 <span data-ttu-id="76fb5-115">[Вход/выход] На входе содержит размер буфера *wszSqlConnection* в символах, включая конечные значения NULL.</span><span class="sxs-lookup"><span data-stu-id="76fb5-115">[Input/Output] On input contains the size of the *wszSqlConnection* buffer in characters, including any trailing nulls.</span></span> <span data-ttu-id="76fb5-116">На выходе, если указан недостаточный размер буфера, содержит требуемый размер буфера в символах, включая любые конечные символы NULL.</span><span class="sxs-lookup"><span data-stu-id="76fb5-116">On output, if the given buffer size is too small, contains the required buffer size in characters, including any trailing nulls.</span></span>  
  
## <a name="returns"></a><span data-ttu-id="76fb5-117">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="76fb5-117">Returns</span></span>  
 <span data-ttu-id="76fb5-118">S_OK</span><span class="sxs-lookup"><span data-stu-id="76fb5-118">S_OK</span></span>  
 <span data-ttu-id="76fb5-119">Функция выполнена успешно.</span><span class="sxs-lookup"><span data-stu-id="76fb5-119">The function succeeded.</span></span>  
  
 [<span data-ttu-id="76fb5-120">LOCALDB_ERROR_NOT_INSTALLED</span><span class="sxs-lookup"><span data-stu-id="76fb5-120">LOCALDB_ERROR_NOT_INSTALLED</span></span>](../express-localdb-error-messages/localdb-error-not-installed.md)  
 <span data-ttu-id="76fb5-121">Компонент SQL Server Express LocalDB не установлен на компьютере.</span><span class="sxs-lookup"><span data-stu-id="76fb5-121">SQL Server Express LocalDB is not installed on the computer.</span></span>  
  
 [<span data-ttu-id="76fb5-122">LOCALDB_ERROR_INVALID_PARAMETER</span><span class="sxs-lookup"><span data-stu-id="76fb5-122">LOCALDB_ERROR_INVALID_PARAMETER</span></span>](../express-localdb-error-messages/localdb-error-invalid-parameter.md)  
 <span data-ttu-id="76fb5-123">Один или несколько указанных входных параметров недопустимы.</span><span class="sxs-lookup"><span data-stu-id="76fb5-123">One or more specified input parameters are invalid.</span></span>  
  
 [<span data-ttu-id="76fb5-124">LOCALDB_ERROR_INVALID_INSTANCE_NAME</span><span class="sxs-lookup"><span data-stu-id="76fb5-124">LOCALDB_ERROR_INVALID_INSTANCE_NAME</span></span>](../express-localdb-error-messages/localdb-error-invalid-instance-name.md)  
 <span data-ttu-id="76fb5-125">Указанное имя экземпляра недопустимо.</span><span class="sxs-lookup"><span data-stu-id="76fb5-125">The specified instance name is invalid.</span></span>  
  
 [<span data-ttu-id="76fb5-126">LOCALDB_ERROR_UNKNOWN_INSTANCE</span><span class="sxs-lookup"><span data-stu-id="76fb5-126">LOCALDB_ERROR_UNKNOWN_INSTANCE</span></span>](../express-localdb-error-messages/localdb-error-unknown-instance.md)  
 <span data-ttu-id="76fb5-127">Экземпляр не существует.</span><span class="sxs-lookup"><span data-stu-id="76fb5-127">The instance does not exist.</span></span>  
  
 [<span data-ttu-id="76fb5-128">LOCALDB_ERROR_INSUFFICIENT_BUFFER</span><span class="sxs-lookup"><span data-stu-id="76fb5-128">LOCALDB_ERROR_INSUFFICIENT_BUFFER</span></span>](../express-localdb-error-messages/localdb-error-insufficient-buffer.md)  
 <span data-ttu-id="76fb5-129">Указан недостаточный размер буфера *wszSqlConnection* .</span><span class="sxs-lookup"><span data-stu-id="76fb5-129">The specified buffer *wszSqlConnection* is too small.</span></span>  
  
 [<span data-ttu-id="76fb5-130">LOCALDB_ERROR_WAIT_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="76fb5-130">LOCALDB_ERROR_WAIT_TIMEOUT</span></span>](../express-localdb-error-messages/localdb-error-wait-timeout.md)  
 <span data-ttu-id="76fb5-131">При попытке получения блокировок синхронизации истекло время ожидания.</span><span class="sxs-lookup"><span data-stu-id="76fb5-131">A time-out occurred while trying to acquire the synchronization locks.</span></span>  
  
 [<span data-ttu-id="76fb5-132">LOCALDB_ERROR_INSTANCE_FOLDER_PATH_TOO_LONG</span><span class="sxs-lookup"><span data-stu-id="76fb5-132">LOCALDB_ERROR_INSTANCE_FOLDER_PATH_TOO_LONG</span></span>](../express-localdb-error-messages/localdb-error-instance-folder-path-too-long.md)  
 <span data-ttu-id="76fb5-133">Длина пути к месту хранения экземпляра больше MAX_PATH.</span><span class="sxs-lookup"><span data-stu-id="76fb5-133">The path where the instance should be stored is longer than MAX_PATH.</span></span>  
  
 [<span data-ttu-id="76fb5-134">LOCALDB_ERROR_CANNOT_GET_USER_PROFILE_FOLDER</span><span class="sxs-lookup"><span data-stu-id="76fb5-134">LOCALDB_ERROR_CANNOT_GET_USER_PROFILE_FOLDER</span></span>](../express-localdb-error-messages/localdb-error-cannot-get-user-profile-folder.md)  
 <span data-ttu-id="76fb5-135">Не удалось получить папку профиля пользователя.</span><span class="sxs-lookup"><span data-stu-id="76fb5-135">A user profile folder cannot be retrieved.</span></span>  
  
 [<span data-ttu-id="76fb5-136">LOCALDB_ERROR_CANNOT_ACCESS_INSTANCE_FOLDER</span><span class="sxs-lookup"><span data-stu-id="76fb5-136">LOCALDB_ERROR_CANNOT_ACCESS_INSTANCE_FOLDER</span></span>](../express-localdb-error-messages/localdb-error-cannot-access-instance-folder.md)  
 <span data-ttu-id="76fb5-137">Не удалось получить доступ к папке экземпляра.</span><span class="sxs-lookup"><span data-stu-id="76fb5-137">An instance folder cannot be accessed.</span></span>  
  
 [<span data-ttu-id="76fb5-138">LOCALDB_ERROR_CANNOT_ACCESS_INSTANCE_REGISTRY</span><span class="sxs-lookup"><span data-stu-id="76fb5-138">LOCALDB_ERROR_CANNOT_ACCESS_INSTANCE_REGISTRY</span></span>](../express-localdb-error-messages/localdb-error-cannot-access-instance-registry.md)  
 <span data-ttu-id="76fb5-139">Не удалось получить доступ к реестру экземпляра.</span><span class="sxs-lookup"><span data-stu-id="76fb5-139">An instance registry cannot be accessed.</span></span>  
  
 [<span data-ttu-id="76fb5-140">LOCALDB_ERROR_CANNOT_MODIFY_INSTANCE_REGISTRY</span><span class="sxs-lookup"><span data-stu-id="76fb5-140">LOCALDB_ERROR_CANNOT_MODIFY_INSTANCE_REGISTRY</span></span>](../express-localdb-error-messages/localdb-error-cannot-modify-instance-registry.md)  
 <span data-ttu-id="76fb5-141">Невозможно изменить реестр экземпляра.</span><span class="sxs-lookup"><span data-stu-id="76fb5-141">An instance registry cannot be modified.</span></span>  
  
 [<span data-ttu-id="76fb5-142">LOCALDB_ERROR_CANNOT_CREATE_SQL_PROCESS</span><span class="sxs-lookup"><span data-stu-id="76fb5-142">LOCALDB_ERROR_CANNOT_CREATE_SQL_PROCESS</span></span>](../express-localdb-error-messages/localdb-error-cannot-create-sql-process.md)  
 <span data-ttu-id="76fb5-143">Не удалось создать процесс для SQL Server.</span><span class="sxs-lookup"><span data-stu-id="76fb5-143">A process for SQL Server cannot be created.</span></span>  
  
 [<span data-ttu-id="76fb5-144">LOCALDB_ERROR_SQL_SERVER_STARTUP_FAILED</span><span class="sxs-lookup"><span data-stu-id="76fb5-144">LOCALDB_ERROR_SQL_SERVER_STARTUP_FAILED</span></span>](../express-localdb-error-messages/localdb-error-sql-server-startup-failed.md)  
 <span data-ttu-id="76fb5-145">Был запущен процесс SQL Server, но запуск SQL Server завершился с ошибкой.</span><span class="sxs-lookup"><span data-stu-id="76fb5-145">A SQL Server process was started, but SQL Server startup failed.</span></span>  
  
 [<span data-ttu-id="76fb5-146">LOCALDB_ERROR_INSTANCE_CONFIGURATION_CORRUPT</span><span class="sxs-lookup"><span data-stu-id="76fb5-146">LOCALDB_ERROR_INSTANCE_CONFIGURATION_CORRUPT</span></span>](../express-localdb-error-messages/localdb-error-instance-configuration-corrupt.md)  
 <span data-ttu-id="76fb5-147">Конфигурация экземпляра была повреждена.</span><span class="sxs-lookup"><span data-stu-id="76fb5-147">An instance configuration was corrupted.</span></span>  
  
 [<span data-ttu-id="76fb5-148">LOCALDB_ERROR_AUTO_INSTANCE_CREATE_FAILED</span><span class="sxs-lookup"><span data-stu-id="76fb5-148">LOCALDB_ERROR_AUTO_INSTANCE_CREATE_FAILED</span></span>](../express-localdb-error-messages/localdb-error-auto-instance-create-failed.md)  
 <span data-ttu-id="76fb5-149">Невозможно создать автоматический экземпляр.</span><span class="sxs-lookup"><span data-stu-id="76fb5-149">Cannot create an automatic instance.</span></span> <span data-ttu-id="76fb5-150">Сведения об ошибке см. в журнале событий приложений Windows.</span><span class="sxs-lookup"><span data-stu-id="76fb5-150">See the Windows Application event log for error details.</span></span>  
  
 [<span data-ttu-id="76fb5-151">LOCALDB_ERROR_INTERNAL_ERROR</span><span class="sxs-lookup"><span data-stu-id="76fb5-151">LOCALDB_ERROR_INTERNAL_ERROR</span></span>](../express-localdb-error-messages/localdb-error-internal-error.md)  
 <span data-ttu-id="76fb5-152">Произошла непредвиденная ошибка.</span><span class="sxs-lookup"><span data-stu-id="76fb5-152">An unexpected error occurred.</span></span> <span data-ttu-id="76fb5-153">Подробные сведения см. в журнале событий.</span><span class="sxs-lookup"><span data-stu-id="76fb5-153">See the event log for details.</span></span>  
  
## <a name="details"></a><span data-ttu-id="76fb5-154">Сведения</span><span class="sxs-lookup"><span data-stu-id="76fb5-154">Details</span></span>  
 <span data-ttu-id="76fb5-155">Аргумент буфера соединения (*wszSqlConnection*) и аргумент размера буфера соединения (*lpcchSqlConnection*) являются необязательными.</span><span class="sxs-lookup"><span data-stu-id="76fb5-155">Both the connection buffer argument (*wszSqlConnection*) and the connection buffer size argument (*lpcchSqlConnection*) are optional.</span></span> <span data-ttu-id="76fb5-156">В следующей таблице показаны варианты использования этих аргументов и их результаты.</span><span class="sxs-lookup"><span data-stu-id="76fb5-156">The following table shows options for using these arguments and their results.</span></span>  
  
|<span data-ttu-id="76fb5-157">Буфер</span><span class="sxs-lookup"><span data-stu-id="76fb5-157">Buffer</span></span>|<span data-ttu-id="76fb5-158">Размер буфера</span><span class="sxs-lookup"><span data-stu-id="76fb5-158">Buffer size</span></span>|<span data-ttu-id="76fb5-159">Правильно</span><span class="sxs-lookup"><span data-stu-id="76fb5-159">Rationale</span></span>|<span data-ttu-id="76fb5-160">Действие</span><span class="sxs-lookup"><span data-stu-id="76fb5-160">Action</span></span>|  
|------------|-----------------|---------------|------------|  
|<span data-ttu-id="76fb5-161">NULL</span><span class="sxs-lookup"><span data-stu-id="76fb5-161">NULL</span></span>|<span data-ttu-id="76fb5-162">NULL</span><span class="sxs-lookup"><span data-stu-id="76fb5-162">NULL</span></span>|<span data-ttu-id="76fb5-163">Пользователь хочет запустить экземпляр и не нуждается в имени канала.</span><span class="sxs-lookup"><span data-stu-id="76fb5-163">User wants to start the instance and doesn't need a pipe name.</span></span>|<span data-ttu-id="76fb5-164">Запускает экземпляр (имя канала и необходимый размер буфера не возвращаются).</span><span class="sxs-lookup"><span data-stu-id="76fb5-164">Starts an instance (no pipe return and no required buffer size return).</span></span>|  
|<span data-ttu-id="76fb5-165">NULL</span><span class="sxs-lookup"><span data-stu-id="76fb5-165">NULL</span></span>|<span data-ttu-id="76fb5-166">Присутствует</span><span class="sxs-lookup"><span data-stu-id="76fb5-166">Present</span></span>|<span data-ttu-id="76fb5-167">Пользователь запрашивает размер выходного буфера.</span><span class="sxs-lookup"><span data-stu-id="76fb5-167">User asks for the output buffer size.</span></span> <span data-ttu-id="76fb5-168">(При следующем вызове пользователь скорее всего запросит запуск).</span><span class="sxs-lookup"><span data-stu-id="76fb5-168">(In the next call the user will probably ask for an actual start.)</span></span>|<span data-ttu-id="76fb5-169">Возвращает требуемый размер буфера (без запуска и возврата канала).</span><span class="sxs-lookup"><span data-stu-id="76fb5-169">Returns a required buffer size (no start and no pipe return).</span></span> <span data-ttu-id="76fb5-170">Результат равен S_OK.</span><span class="sxs-lookup"><span data-stu-id="76fb5-170">Result is S_OK.</span></span>|  
|<span data-ttu-id="76fb5-171">Присутствует</span><span class="sxs-lookup"><span data-stu-id="76fb5-171">Present</span></span>|<span data-ttu-id="76fb5-172">NULL</span><span class="sxs-lookup"><span data-stu-id="76fb5-172">NULL</span></span>|<span data-ttu-id="76fb5-173">Недопустимо; неверный вход.</span><span class="sxs-lookup"><span data-stu-id="76fb5-173">Not allowed; incorrect input.</span></span>|<span data-ttu-id="76fb5-174">Возвращаемый результат — LOCALDB_ERROR_INVALID_PARAMETER.</span><span class="sxs-lookup"><span data-stu-id="76fb5-174">Returned result is LOCALDB_ERROR_INVALID_PARAMETER.</span></span>|  
|<span data-ttu-id="76fb5-175">Присутствует</span><span class="sxs-lookup"><span data-stu-id="76fb5-175">Present</span></span>|<span data-ttu-id="76fb5-176">Присутствует</span><span class="sxs-lookup"><span data-stu-id="76fb5-176">Present</span></span>|<span data-ttu-id="76fb5-177">Пользователь хочет запустить экземпляр и нуждается в имени канала для подключения к нему после запуска.</span><span class="sxs-lookup"><span data-stu-id="76fb5-177">User wants to start the instance and needs the pipe name to connect to it after it is started.</span></span>|<span data-ttu-id="76fb5-178">Проверяет размер буфера, запускает экземпляр и возвращает имя канала в буфере.</span><span class="sxs-lookup"><span data-stu-id="76fb5-178">Checks the buffer size, starts the instance, and returns the pipe name in the buffer.</span></span> <br /><span data-ttu-id="76fb5-179">Аргумент размера буфера возвращает длину строки "Server =", не включая завершающие значения NULL.</span><span class="sxs-lookup"><span data-stu-id="76fb5-179">The buffer size argument returns the length of the "server=" string, not including terminating nulls.</span></span>|  
  
 <span data-ttu-id="76fb5-180">Образец кода, использующего API LocalDB, см. в разделе [SQL Server Express LocalDB Reference](../sql-server-express-localdb-reference.md)</span><span class="sxs-lookup"><span data-stu-id="76fb5-180">For a code sample that uses LocalDB API, see [SQL Server Express LocalDB Reference](../sql-server-express-localdb-reference.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="76fb5-181">См. также:</span><span class="sxs-lookup"><span data-stu-id="76fb5-181">See Also</span></span>  
 [<span data-ttu-id="76fb5-182">Заголовок и сведения о версии SQL Server Express LocalDB</span><span class="sxs-lookup"><span data-stu-id="76fb5-182">SQL Server Express LocalDB Header and Version Information</span></span>](sql-server-express-localdb-header-and-version-information.md)  
  
  
