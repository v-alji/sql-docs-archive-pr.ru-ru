---
title: Функция LocalDBGetInstanceInfo | Документация Майкрософт
ms.custom: ''
ms.date: 03/08/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: reference
api_name:
- LocalDBGetInstanceInfo
api_location:
- sqluserinstance.dll
topic_type:
- apiref
ms.assetid: 231706f5-26c6-42eb-ab47-315df6b8f824
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: dc7cbe2c59a7502a1fd0c8b4f92fb14e5defd50b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87657112"
---
# <a name="localdbgetinstanceinfo-function"></a><span data-ttu-id="4c7ca-102">Функция LocalDBGetInstanceInfo</span><span class="sxs-lookup"><span data-stu-id="4c7ca-102">LocalDBGetInstanceInfo Function</span></span>
  <span data-ttu-id="4c7ca-103">Возвращает сведения об указанном экземпляре среды выполнения экземпляра SQL Server Express LocalDB, в частности существует ли этот экземпляр, версия используемой им LocalDB, запущен ли экземпляр и т. п.</span><span class="sxs-lookup"><span data-stu-id="4c7ca-103">Returns information for the specified SQL Server Express LocalDB instance, such as whether it exists, the LocalDB version it uses, whether it is running, and so on.</span></span>  
  
 <span data-ttu-id="4c7ca-104">Эти сведения возвращаются в `struct` именованном **локалдбинстанцеинфо**, который имеет следующее определение.</span><span class="sxs-lookup"><span data-stu-id="4c7ca-104">The information is returned in a `struct` named **LocalDBInstanceInfo**, which has the following definition.</span></span>  
  
```  
typedef struct _LocalDBInstanceInfo  
{  
      // Contains the size of the LocalDBInstanceInfo struct  
      DWORD  cbLocalDBInstanceInfoSize;  
  
      // Holds the instance name  
      TLocalDBInstanceNamewszInstanceName;  
  
      // TRUE if the instance files exist on disk, FALSE otherwise  
      BOOL   bExists;  
  
      // TRUE if the instance configuration registry is corrupted, FALSE otherwise  
      BOOLbConfigurationCorrupted;  
  
      // TRUE if the instance is running at the moment, FALSE otherwise  
      BOOL   bIsRunning;  
  
      // Holds the LocalDB version for the instance in the format: major.minor.build.revision  
      DWORD  dwMajor;  
      DWORD  dwMinor;  
      DWORD  dwBuild;  
      DWORD  dwRevision;  
  
      // Holds the date and time when the instance was started for the last time  
      FILETIME ftLastStartUTC;  
  
      // Holds the name of the TDS named pipe to connect to the instance  
      WCHARwszConnection;  
  
      // TRUE if the instance is shared, FALSE otherwise  
      BOOLbIsShared;  
  
      // Holds the shared name for the instance (if the instance is shared)  
      TLocalDBInstanceNamewszSharedInstanceName;  
  
      // Holds the SID of the instance owner (if the instance is shared)  
      WCHARwszOwnerSID;   
  
      // TRUE if the instance is Automatic, FALSE otherwise  
      BOOLbIsAutomatic;  
} LocalDBInstanceInfo;  
  
```  
  
 <span data-ttu-id="4c7ca-105">**Файл заголовка:** sqlncli.h</span><span class="sxs-lookup"><span data-stu-id="4c7ca-105">**Header file:** sqlncli.h</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4c7ca-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="4c7ca-106">Syntax</span></span>  
  
```  
HRESULT LocalDBGetInstanceInfo(  
           PCWSTR wszInstanceName,  
           PLocalDBInstanceInfo pInstanceInfo,  
           DWORD dwInstanceInfoSize   
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="4c7ca-107">Параметры</span><span class="sxs-lookup"><span data-stu-id="4c7ca-107">Parameters</span></span>  
 <span data-ttu-id="4c7ca-108">*всзинстанценаме*</span><span class="sxs-lookup"><span data-stu-id="4c7ca-108">*wszInstanceName*</span></span>  
 <span data-ttu-id="4c7ca-109">[Вход] Имя экземпляра.</span><span class="sxs-lookup"><span data-stu-id="4c7ca-109">[Input] The instance name.</span></span>  
  
 <span data-ttu-id="4c7ca-110">*пинстанцеинфо*</span><span class="sxs-lookup"><span data-stu-id="4c7ca-110">*pInstanceInfo*</span></span>  
 <span data-ttu-id="4c7ca-111">[Выход] Буфер для сохранения сведений об экземпляре LocalDB.</span><span class="sxs-lookup"><span data-stu-id="4c7ca-111">[Output] The buffer to store the information about the LocalDB instance.</span></span>  
  
 <span data-ttu-id="4c7ca-112">*двинстанцеинфосизе*</span><span class="sxs-lookup"><span data-stu-id="4c7ca-112">*dwInstanceInfoSize*</span></span>  
 <span data-ttu-id="4c7ca-113">Входной Содержит размер буфера *инстанцеинфо* .</span><span class="sxs-lookup"><span data-stu-id="4c7ca-113">[Input] Holds the size of the *InstanceInfo* buffer.</span></span>  
  
## <a name="returns"></a><span data-ttu-id="4c7ca-114">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="4c7ca-114">Returns</span></span>  
 <span data-ttu-id="4c7ca-115">S_OK</span><span class="sxs-lookup"><span data-stu-id="4c7ca-115">S_OK</span></span>  
 <span data-ttu-id="4c7ca-116">Функция выполнена успешно.</span><span class="sxs-lookup"><span data-stu-id="4c7ca-116">The function succeeded.</span></span>  
  
 [<span data-ttu-id="4c7ca-117">LOCALDB_ERROR_NOT_INSTALLED</span><span class="sxs-lookup"><span data-stu-id="4c7ca-117">LOCALDB_ERROR_NOT_INSTALLED</span></span>](../express-localdb-error-messages/localdb-error-not-installed.md)  
 <span data-ttu-id="4c7ca-118">Компонент SQL Server Express LocalDB не установлен на компьютере.</span><span class="sxs-lookup"><span data-stu-id="4c7ca-118">SQL Server Express LocalDB is not installed on the computer.</span></span>  
  
 [<span data-ttu-id="4c7ca-119">LOCALDB_ERROR_INVALID_PARAMETER</span><span class="sxs-lookup"><span data-stu-id="4c7ca-119">LOCALDB_ERROR_INVALID_PARAMETER</span></span>](../express-localdb-error-messages/localdb-error-invalid-parameter.md)  
 <span data-ttu-id="4c7ca-120">Один или несколько указанных входных параметров недопустимы.</span><span class="sxs-lookup"><span data-stu-id="4c7ca-120">One or more specified input parameters are invalid.</span></span>  
  
 [<span data-ttu-id="4c7ca-121">LOCALDB_ERROR_INVALID_INSTANCE_NAME</span><span class="sxs-lookup"><span data-stu-id="4c7ca-121">LOCALDB_ERROR_INVALID_INSTANCE_NAME</span></span>](../express-localdb-error-messages/localdb-error-invalid-instance-name.md)  
 <span data-ttu-id="4c7ca-122">Указанное имя экземпляра недопустимо.</span><span class="sxs-lookup"><span data-stu-id="4c7ca-122">The specified instance name is invalid.</span></span>  
  
 [<span data-ttu-id="4c7ca-123">LOCALDB_ERROR_UNKNOWN_INSTANCE</span><span class="sxs-lookup"><span data-stu-id="4c7ca-123">LOCALDB_ERROR_UNKNOWN_INSTANCE</span></span>](../express-localdb-error-messages/localdb-error-unknown-instance.md)  
 <span data-ttu-id="4c7ca-124">Экземпляр не существует.</span><span class="sxs-lookup"><span data-stu-id="4c7ca-124">The instance does not exist.</span></span>  
  
 [<span data-ttu-id="4c7ca-125">LOCALDB_ERROR_INSTANCE_FOLDER_PATH_TOO_LONG</span><span class="sxs-lookup"><span data-stu-id="4c7ca-125">LOCALDB_ERROR_INSTANCE_FOLDER_PATH_TOO_LONG</span></span>](../express-localdb-error-messages/localdb-error-instance-folder-path-too-long.md)  
 <span data-ttu-id="4c7ca-126">Длина пути к месту хранения экземпляра больше MAX_PATH.</span><span class="sxs-lookup"><span data-stu-id="4c7ca-126">The path where the instance should be stored is longer than MAX_PATH.</span></span>  
  
 [<span data-ttu-id="4c7ca-127">LOCALDB_ERROR_CANNOT_ACCESS_INSTANCE_FOLDER</span><span class="sxs-lookup"><span data-stu-id="4c7ca-127">LOCALDB_ERROR_CANNOT_ACCESS_INSTANCE_FOLDER</span></span>](../express-localdb-error-messages/localdb-error-cannot-access-instance-folder.md)  
 <span data-ttu-id="4c7ca-128">Не удалось получить доступ к папке экземпляра.</span><span class="sxs-lookup"><span data-stu-id="4c7ca-128">An instance folder cannot be accessed.</span></span>  
  
 [<span data-ttu-id="4c7ca-129">LOCALDB_ERROR_CANNOT_ACCESS_INSTANCE_REGISTRY</span><span class="sxs-lookup"><span data-stu-id="4c7ca-129">LOCALDB_ERROR_CANNOT_ACCESS_INSTANCE_REGISTRY</span></span>](../express-localdb-error-messages/localdb-error-cannot-access-instance-registry.md)  
 <span data-ttu-id="4c7ca-130">Не удалось получить доступ к реестру экземпляра.</span><span class="sxs-lookup"><span data-stu-id="4c7ca-130">An instance registry cannot be accessed.</span></span>  
  
 [<span data-ttu-id="4c7ca-131">LOCALDB_ERROR_INSTANCE_CONFIGURATION_CORRUPT</span><span class="sxs-lookup"><span data-stu-id="4c7ca-131">LOCALDB_ERROR_INSTANCE_CONFIGURATION_CORRUPT</span></span>](../express-localdb-error-messages/localdb-error-instance-configuration-corrupt.md)  
 <span data-ttu-id="4c7ca-132">Конфигурация экземпляра повреждена.</span><span class="sxs-lookup"><span data-stu-id="4c7ca-132">An instance configuration is corrupted.</span></span>  
  
 [<span data-ttu-id="4c7ca-133">LOCALDB_ERROR_INTERNAL_ERROR</span><span class="sxs-lookup"><span data-stu-id="4c7ca-133">LOCALDB_ERROR_INTERNAL_ERROR</span></span>](../express-localdb-error-messages/localdb-error-internal-error.md)  
 <span data-ttu-id="4c7ca-134">Произошла непредвиденная ошибка.</span><span class="sxs-lookup"><span data-stu-id="4c7ca-134">An unexpected error occurred.</span></span> <span data-ttu-id="4c7ca-135">Подробные сведения см. в журнале событий.</span><span class="sxs-lookup"><span data-stu-id="4c7ca-135">See the event log for details.</span></span>  
  
## <a name="details"></a><span data-ttu-id="4c7ca-136">Сведения</span><span class="sxs-lookup"><span data-stu-id="4c7ca-136">Details</span></span>  
 <span data-ttu-id="4c7ca-137">Смысл в поведении `struct` аргумента size (*лпинстанцеинфосизе*) заключается в том, чтобы позволить API возвращать различные версии **локалдбинстанцеинфострукт**, эффективно обеспечивая прямую и обратную совместимость.</span><span class="sxs-lookup"><span data-stu-id="4c7ca-137">The rationale behind the introduction of the `struct` size argument (*lpInstanceInfoSize*) is to enable the API to return different versions of the **LocalDBInstanceInfostruct**, effectively enabling forward and backward compatibility.</span></span>  
  
 <span data-ttu-id="4c7ca-138">Если `struct` аргумент size (*лпинстанцеинфосизе*) соответствует размеру известной версии **локалдбинстанцеинфострукт**, возвращается эта версия `struct` .</span><span class="sxs-lookup"><span data-stu-id="4c7ca-138">If the `struct` size argument (*lpInstanceInfoSize*) matches the size of a known version of the **LocalDBInstanceInfostruct**, that version of the `struct` is returned.</span></span> <span data-ttu-id="4c7ca-139">В противном случае возвращается значение LOCALDB_ERROR_INVALID_PARAMETER.</span><span class="sxs-lookup"><span data-stu-id="4c7ca-139">Otherwise, LOCALDB_ERROR_INVALID_PARAMETER is returned.</span></span>  
  
 <span data-ttu-id="4c7ca-140">Типичный пример использования API **LocalDBGetInstanceInfo** выглядит следующим образом:</span><span class="sxs-lookup"><span data-stu-id="4c7ca-140">A typical example of **LocalDBGetInstanceInfo** API usage looks like this:</span></span>  
  
```  
LocalDBInstanceInfo ii;  
LocalDBInstanceInfo(L"Test", &ii, sizeof(LocalDBInstanceInfo));  
  
```  
  
 <span data-ttu-id="4c7ca-141">Образец кода, использующего API LocalDB, см. в разделе [SQL Server Express LocalDB Reference](../sql-server-express-localdb-reference.md)</span><span class="sxs-lookup"><span data-stu-id="4c7ca-141">For a code sample that uses LocalDB API, see [SQL Server Express LocalDB Reference](../sql-server-express-localdb-reference.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4c7ca-142">См. также:</span><span class="sxs-lookup"><span data-stu-id="4c7ca-142">See Also</span></span>  
 [<span data-ttu-id="4c7ca-143">Заголовок и сведения о версии SQL Server Express LocalDB</span><span class="sxs-lookup"><span data-stu-id="4c7ca-143">SQL Server Express LocalDB Header and Version Information</span></span>](sql-server-express-localdb-header-and-version-information.md)  
  
  
