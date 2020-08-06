---
title: Функция Localdbgetversionsinfo | Документация Майкрософт
ms.custom: ''
ms.date: 03/08/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: reference
api_name:
- LocalDBGetVersionInfo
api_location:
- sqluserinstance.dll
topic_type:
- apiref
ms.assetid: d4aaea30-1d0d-4436-bcdc-5c101d27b1c1
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: e30bb4dcd4c258db899883f650dbfe7100171ef8
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87751047"
---
# <a name="localdbgetversioninfo-function"></a><span data-ttu-id="d4baf-102">Функция LocalDBGetVersionsInfo</span><span class="sxs-lookup"><span data-stu-id="d4baf-102">LocalDBGetVersionInfo Function</span></span>
  <span data-ttu-id="d4baf-103">Возвращает сведения для указанной версии SQL Server Express LocalDB — факт ее существования и полный номер версии LocalDB (включая номер сборки и номер выпуска).</span><span class="sxs-lookup"><span data-stu-id="d4baf-103">Returns information for the specified SQL Server Express LocalDB version, such as whether it exists and the full LocalDB version number (including build and release numbers).</span></span>  
  
 <span data-ttu-id="d4baf-104">Эти сведения возвращаются в виде `struct` именованной **локалдбверсионинфо**, которая имеет следующее определение.</span><span class="sxs-lookup"><span data-stu-id="d4baf-104">The information is returned in the form of a `struct` named **LocalDBVersionInfo**, which has the following definition.</span></span>  
  
```  
typedef struct _LocalDBVersionInfo  
{  
      // Contains the size of the LocalDBVersionInfo struct  
      DWORD  cbLocalDBVersionInfoSize;  
  
      // Holds the version name  
      TLocalDBVersionwszVersion;  
  
      // TRUE if the instance files exist on disk, FALSE otherwise  
      BOOL   bExists;  
  
      // Holds the LocalDB version for the instance in the format: major.minor.build.revision  
      DWORD  dwMajor;  
      DWORD  dwMinor;  
      DWORD  dwBuild;  
      DWORD  dwRevision;  
} LocalDBVersionInfo;  
  
```  
  
 <span data-ttu-id="d4baf-105">**Файл заголовка:** sqlncli.h</span><span class="sxs-lookup"><span data-stu-id="d4baf-105">**Header file:** sqlncli.h</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d4baf-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="d4baf-106">Syntax</span></span>  
  
```  
HRESULT LocalDBGetVersionInfo(  
           PCWSTR wszVersionName,           PLocalDBVersionInfo pVersionInfo,           DWORD dwVersionInfoSize);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d4baf-107">Параметры</span><span class="sxs-lookup"><span data-stu-id="d4baf-107">Parameters</span></span>  
 <span data-ttu-id="d4baf-108">*всзверсионнаме*</span><span class="sxs-lookup"><span data-stu-id="d4baf-108">*wszVersionName*</span></span>  
 <span data-ttu-id="d4baf-109">[Вход] Имя версии LocalDB.</span><span class="sxs-lookup"><span data-stu-id="d4baf-109">[Input] The LocalDB version name.</span></span>  
  
 <span data-ttu-id="d4baf-110">*пверсионинфо*</span><span class="sxs-lookup"><span data-stu-id="d4baf-110">*pVersionInfo*</span></span>  
 <span data-ttu-id="d4baf-111">[Выход] Буфер для хранения сведений о версии LocalDB.</span><span class="sxs-lookup"><span data-stu-id="d4baf-111">[Output] The buffer to store the information about the LocalDB version.</span></span>  
  
 <span data-ttu-id="d4baf-112">*двверсионинфосизе*</span><span class="sxs-lookup"><span data-stu-id="d4baf-112">*dwVersionInfoSize*</span></span>  
 <span data-ttu-id="d4baf-113">Входной Содержит размер буфера *versionInfo* .</span><span class="sxs-lookup"><span data-stu-id="d4baf-113">[Input] Holds the size of the *VersionInfo* buffer.</span></span>  
  
## <a name="returns"></a><span data-ttu-id="d4baf-114">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="d4baf-114">Returns</span></span>  
 <span data-ttu-id="d4baf-115">S_OK</span><span class="sxs-lookup"><span data-stu-id="d4baf-115">S_OK</span></span>  
 <span data-ttu-id="d4baf-116">Функция выполнена успешно.</span><span class="sxs-lookup"><span data-stu-id="d4baf-116">The function succeeded.</span></span>  
  
 [<span data-ttu-id="d4baf-117">LOCALDB_ERROR_NOT_INSTALLED</span><span class="sxs-lookup"><span data-stu-id="d4baf-117">LOCALDB_ERROR_NOT_INSTALLED</span></span>](../express-localdb-error-messages/localdb-error-not-installed.md)  
 <span data-ttu-id="d4baf-118">Компонент SQL Server Express LocalDB не установлен на компьютере.</span><span class="sxs-lookup"><span data-stu-id="d4baf-118">SQL Server Express LocalDB is not installed on the computer.</span></span>  
  
 [<span data-ttu-id="d4baf-119">LOCALDB_ERROR_INVALID_PARAMETER</span><span class="sxs-lookup"><span data-stu-id="d4baf-119">LOCALDB_ERROR_INVALID_PARAMETER</span></span>](../express-localdb-error-messages/localdb-error-invalid-parameter.md)  
 <span data-ttu-id="d4baf-120">Один или несколько указанных входных параметров недопустимы.</span><span class="sxs-lookup"><span data-stu-id="d4baf-120">One or more specified input parameters are invalid.</span></span>  
  
 [<span data-ttu-id="d4baf-121">LOCALDB_ERROR_UNKNOWN_VERSION</span><span class="sxs-lookup"><span data-stu-id="d4baf-121">LOCALDB_ERROR_UNKNOWN_VERSION</span></span>](../express-localdb-error-messages/localdb-error-unknown-version.md)  
 <span data-ttu-id="d4baf-122">Указанная версия LocalDB не существует.</span><span class="sxs-lookup"><span data-stu-id="d4baf-122">The specified LocalDB version does not exist.</span></span>  
  
 [<span data-ttu-id="d4baf-123">LOCALDB_ERROR_INTERNAL_ERROR</span><span class="sxs-lookup"><span data-stu-id="d4baf-123">LOCALDB_ERROR_INTERNAL_ERROR</span></span>](../express-localdb-error-messages/localdb-error-internal-error.md)  
 <span data-ttu-id="d4baf-124">Произошла непредвиденная ошибка.</span><span class="sxs-lookup"><span data-stu-id="d4baf-124">An unexpected error occurred.</span></span> <span data-ttu-id="d4baf-125">Подробные сведения см. в журнале событий.</span><span class="sxs-lookup"><span data-stu-id="d4baf-125">See the event log for details.</span></span>  
  
## <a name="details"></a><span data-ttu-id="d4baf-126">Сведения</span><span class="sxs-lookup"><span data-stu-id="d4baf-126">Details</span></span>  
 <span data-ttu-id="d4baf-127">Смысл в поведении `struct` аргумента size (*лпверсионинфосизе*) заключается в том, чтобы позволить API возвращать различные версии **локалдбверсионинфострукт**, эффективно обеспечивая прямую и обратную совместимость.</span><span class="sxs-lookup"><span data-stu-id="d4baf-127">The rationale behind the introduction of the `struct` size argument (*lpVersionInfoSize*) is to enable the API to return different versions of the **LocalDBVersionInfostruct**, effectively enabling forward and backward compatibility.</span></span>  
  
 <span data-ttu-id="d4baf-128">Если `struct` аргумент size (*лпверсионинфосизе*) соответствует размеру известной версии **локалдбверсионинфострукт**, возвращается эта версия `struct` .</span><span class="sxs-lookup"><span data-stu-id="d4baf-128">If the `struct` size argument (*lpVersionInfoSize*) matches the size of a known version of the **LocalDBVersionInfostruct**, that version of the `struct` is returned.</span></span> <span data-ttu-id="d4baf-129">В противном случае возвращается значение LOCALDB_ERROR_INVALID_PARAMETER.</span><span class="sxs-lookup"><span data-stu-id="d4baf-129">Otherwise, LOCALDB_ERROR_INVALID_PARAMETER is returned.</span></span>  
  
 <span data-ttu-id="d4baf-130">Типичный пример использования API **localdbgetversionsinfo** выглядит следующим образом:</span><span class="sxs-lookup"><span data-stu-id="d4baf-130">A typical example of **LocalDBGetVersionInfo** API usage looks like this:</span></span>  
  
```  
LocalDBVersionInfo vi;  
LocalDBVersionInfo(L"11.0", &vi, sizeof(LocalDBVersionInfo));  
  
```  
  
## <a name="remarks"></a><span data-ttu-id="d4baf-131">Remarks</span><span class="sxs-lookup"><span data-stu-id="d4baf-131">Remarks</span></span>  
 <span data-ttu-id="d4baf-132">Образец кода, использующего API LocalDB, см. в разделе [SQL Server Express LocalDB Reference](../sql-server-express-localdb-reference.md)</span><span class="sxs-lookup"><span data-stu-id="d4baf-132">For a code sample that uses LocalDB API, see [SQL Server Express LocalDB Reference](../sql-server-express-localdb-reference.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d4baf-133">См. также:</span><span class="sxs-lookup"><span data-stu-id="d4baf-133">See Also</span></span>  
 [<span data-ttu-id="d4baf-134">Заголовок и сведения о версии SQL Server Express LocalDB</span><span class="sxs-lookup"><span data-stu-id="d4baf-134">SQL Server Express LocalDB Header and Version Information</span></span>](sql-server-express-localdb-header-and-version-information.md)  
  
  
