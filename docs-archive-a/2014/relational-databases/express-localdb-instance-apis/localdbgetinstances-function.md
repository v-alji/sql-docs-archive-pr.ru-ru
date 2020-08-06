---
title: Функция Локалдбжетинстанцес | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: reference
api_name:
- LocalDBGetInstances
api_location:
- sqluserinstance.dll
topic_type:
- apiref
ms.assetid: f95a9980-8bc0-426c-8aa1-e2660b6784cf
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: 4a6f758bd647fd69a14f72a0651bb3e2e33a7c79
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87728257"
---
# <a name="localdbgetinstances-function"></a><span data-ttu-id="a2184-102">Функция LocalDBGetInstances</span><span class="sxs-lookup"><span data-stu-id="a2184-102">LocalDBGetInstances Function</span></span>
  <span data-ttu-id="a2184-103">Возвращает все экземпляры SQL Server Express LocalDB с данной версией.</span><span class="sxs-lookup"><span data-stu-id="a2184-103">Returns all SQL Server Express LocalDB instances with the given version.</span></span>  
  
 <span data-ttu-id="a2184-104">**Файл заголовка:** sqlncli.h</span><span class="sxs-lookup"><span data-stu-id="a2184-104">**Header file:** sqlncli.h</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a2184-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="a2184-105">Syntax</span></span>  
  
```  
#define MAX_LOCALDB_INSTANCE_NAME_LENGTH 128typedef WCHAR TLocalDBInstanceName[MAX_LOCALDB_INSTANCE_NAME_LENGTH + 1];typedef TLocalDBInstanceName* PTLocalDBInstanceName;  
HRESULT LocalDBGetInstances(  
           PTLocalDBInstanceName pInstanceNames,  
           LPDWORD lpdwNumberOfInstances  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a2184-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="a2184-106">Parameters</span></span>  
 <span data-ttu-id="a2184-107">*pInstanceNames*</span><span class="sxs-lookup"><span data-stu-id="a2184-107">*pInstanceNames*</span></span>  
 <span data-ttu-id="a2184-108">Проверки При возврате этой функции содержит имена как именованных, так и экземпляров LocalDB по умолчанию на рабочей станции пользователя.</span><span class="sxs-lookup"><span data-stu-id="a2184-108">[Output] When this function returns, contains the names of both named and default LocalDB instances on the user's workstation.</span></span>  
  
 <span data-ttu-id="a2184-109">*лпдвнумберофинстанцес*</span><span class="sxs-lookup"><span data-stu-id="a2184-109">*lpdwNumberOfInstances*</span></span>  
 <span data-ttu-id="a2184-110">[Вход/Выход] На входе содержит число ячеек для имен экземпляров в буфере *pInstanceNames* .</span><span class="sxs-lookup"><span data-stu-id="a2184-110">[Input/Output] On input, contains the number of slots for instance names in the *pInstanceNames* buffer.</span></span> <span data-ttu-id="a2184-111">На выходе содержит количество экземпляров LocalDB, найденных на рабочей станции пользователя.</span><span class="sxs-lookup"><span data-stu-id="a2184-111">On output, contains the number of LocalDB instances found on the user's workstation.</span></span>  
  
## <a name="returns"></a><span data-ttu-id="a2184-112">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="a2184-112">Returns</span></span>  
 <span data-ttu-id="a2184-113">S_OK</span><span class="sxs-lookup"><span data-stu-id="a2184-113">S_OK</span></span>  
 <span data-ttu-id="a2184-114">Функция выполнена успешно.</span><span class="sxs-lookup"><span data-stu-id="a2184-114">The function succeeded.</span></span>  
  
 [<span data-ttu-id="a2184-115">LOCALDB_ERROR_NOT_INSTALLED</span><span class="sxs-lookup"><span data-stu-id="a2184-115">LOCALDB_ERROR_NOT_INSTALLED</span></span>](../express-localdb-error-messages/localdb-error-not-installed.md)  
 <span data-ttu-id="a2184-116">Компонент SQL Server Express LocalDB не установлен на компьютере.</span><span class="sxs-lookup"><span data-stu-id="a2184-116">SQL Server Express LocalDB is not installed on the computer.</span></span>  
  
 [<span data-ttu-id="a2184-117">LOCALDB_ERROR_INVALID_PARAMETER</span><span class="sxs-lookup"><span data-stu-id="a2184-117">LOCALDB_ERROR_INVALID_PARAMETER</span></span>](../express-localdb-error-messages/localdb-error-invalid-parameter.md)  
 <span data-ttu-id="a2184-118">Один или несколько указанных входных параметров недопустимы.</span><span class="sxs-lookup"><span data-stu-id="a2184-118">One or more specified input parameters are invalid.</span></span>  
  
 [<span data-ttu-id="a2184-119">LOCALDB_ERROR_INSUFFICIENT_BUFFER</span><span class="sxs-lookup"><span data-stu-id="a2184-119">LOCALDB_ERROR_INSUFFICIENT_BUFFER</span></span>](../express-localdb-error-messages/localdb-error-insufficient-buffer.md)  
 <span data-ttu-id="a2184-120">Размер входного буфера является недостаточным, а усечение не было запрошено.</span><span class="sxs-lookup"><span data-stu-id="a2184-120">The input buffer is too short, and truncation was not requested.</span></span>  
  
 [<span data-ttu-id="a2184-121">LOCALDB_ERROR_INSTANCE_FOLDER_PATH_TOO_LONG</span><span class="sxs-lookup"><span data-stu-id="a2184-121">LOCALDB_ERROR_INSTANCE_FOLDER_PATH_TOO_LONG</span></span>](../express-localdb-error-messages/localdb-error-instance-folder-path-too-long.md)  
 <span data-ttu-id="a2184-122">Длина пути к месту хранения экземпляра больше MAX_PATH.</span><span class="sxs-lookup"><span data-stu-id="a2184-122">The path where the instance should be stored is longer than MAX_PATH.</span></span>  
  
 [<span data-ttu-id="a2184-123">LOCALDB_ERROR_CANNOT_ACCESS_INSTANCE_REGISTRY</span><span class="sxs-lookup"><span data-stu-id="a2184-123">LOCALDB_ERROR_CANNOT_ACCESS_INSTANCE_REGISTRY</span></span>](../express-localdb-error-messages/localdb-error-cannot-access-instance-registry.md)  
 <span data-ttu-id="a2184-124">Не удалось получить доступ к реестру экземпляра.</span><span class="sxs-lookup"><span data-stu-id="a2184-124">An instance registry cannot be accessed.</span></span>  
  
 [<span data-ttu-id="a2184-125">LOCALDB_ERROR_INSTANCE_CONFIGURATION_CORRUPT</span><span class="sxs-lookup"><span data-stu-id="a2184-125">LOCALDB_ERROR_INSTANCE_CONFIGURATION_CORRUPT</span></span>](../express-localdb-error-messages/localdb-error-instance-configuration-corrupt.md)  
 <span data-ttu-id="a2184-126">Конфигурация экземпляра повреждена.</span><span class="sxs-lookup"><span data-stu-id="a2184-126">An instance configuration is corrupted.</span></span>  
  
 [<span data-ttu-id="a2184-127">LOCALDB_ERROR_INTERNAL_ERROR</span><span class="sxs-lookup"><span data-stu-id="a2184-127">LOCALDB_ERROR_INTERNAL_ERROR</span></span>](../express-localdb-error-messages/localdb-error-internal-error.md)  
 <span data-ttu-id="a2184-128">Произошла непредвиденная ошибка.</span><span class="sxs-lookup"><span data-stu-id="a2184-128">An unexpected error occurred.</span></span> <span data-ttu-id="a2184-129">Подробные сведения см. в журнале событий.</span><span class="sxs-lookup"><span data-stu-id="a2184-129">See the event log for details.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a2184-130">Remarks</span><span class="sxs-lookup"><span data-stu-id="a2184-130">Remarks</span></span>  
 <span data-ttu-id="a2184-131">Образец кода, использующего API LocalDB, см. в разделе [SQL Server Express LocalDB Reference](../sql-server-express-localdb-reference.md)</span><span class="sxs-lookup"><span data-stu-id="a2184-131">For a code sample that uses LocalDB API, see [SQL Server Express LocalDB Reference](../sql-server-express-localdb-reference.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a2184-132">См. также:</span><span class="sxs-lookup"><span data-stu-id="a2184-132">See Also</span></span>  
 [<span data-ttu-id="a2184-133">Заголовок и сведения о версии SQL Server Express LocalDB</span><span class="sxs-lookup"><span data-stu-id="a2184-133">SQL Server Express LocalDB Header and Version Information</span></span>](sql-server-express-localdb-header-and-version-information.md)  
  
  
