---
title: Функция LocalDBFormatMessage | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: reference
api_name:
- LocalDBFormatMessage
api_location:
- sqluserinstance.dll
topic_type:
- apiref
ms.assetid: 31b3152a-94cf-4f75-a31b-296d7dd16dbe
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: ece28f19e3488fae248bf26c3a54a018ba6efd0c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87752160"
---
# <a name="localdbformatmessage-function"></a><span data-ttu-id="64764-102">Функция LocalDBFormatMessage</span><span class="sxs-lookup"><span data-stu-id="64764-102">LocalDBFormatMessage Function</span></span>
  <span data-ttu-id="64764-103">Возвращает локализованное текстовое описание для указанной ошибки SQL Server Express LocalDB.</span><span class="sxs-lookup"><span data-stu-id="64764-103">Returns the localized textual description for the specified SQL Server Express LocalDB error.</span></span>  
  
 <span data-ttu-id="64764-104">**Файл заголовка:** sqlncli.h</span><span class="sxs-lookup"><span data-stu-id="64764-104">**Header file:** sqlncli.h</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="64764-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="64764-105">Syntax</span></span>  
  
```  
HRESULT LocalDBFormatMessage(  
           HRESULT hrLocalDB,  
           DWORD dwFlags,   
           DWORD dwLanguageId,   
           LPWSTR wszMessage,   
           LPDWORD lpcchMessage   
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="64764-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="64764-106">Parameters</span></span>  
 <span data-ttu-id="64764-107">*хрлокалдб*</span><span class="sxs-lookup"><span data-stu-id="64764-107">*hrLocalDB*</span></span>  
 <span data-ttu-id="64764-108">[Вход] Код ошибки LocalDB.</span><span class="sxs-lookup"><span data-stu-id="64764-108">[Input] The LocalDB error code.</span></span>  
  
 <span data-ttu-id="64764-109">*dwFlags*</span><span class="sxs-lookup"><span data-stu-id="64764-109">*dwFlags*</span></span>  
 <span data-ttu-id="64764-110">[Вход] Флаги, задающие поведение этой функции.</span><span class="sxs-lookup"><span data-stu-id="64764-110">[Input] The flags specifying the behavior of this function.</span></span>  
  
 <span data-ttu-id="64764-111">Доступные флаги:</span><span class="sxs-lookup"><span data-stu-id="64764-111">Available flags:</span></span>  
  
 <span data-ttu-id="64764-112">LOCALDB_TRUNCATE_ERR_MESSAGE</span><span class="sxs-lookup"><span data-stu-id="64764-112">LOCALDB_TRUNCATE_ERR_MESSAGE</span></span>  
 <span data-ttu-id="64764-113">Если размер входного буфера окажется недостаточным, сообщение об ошибке урезается до длины буфера.</span><span class="sxs-lookup"><span data-stu-id="64764-113">If the input buffer is too short, the error message will be truncated to fit the buffer.</span></span>  
  
 <span data-ttu-id="64764-114">*двлангуажеид*</span><span class="sxs-lookup"><span data-stu-id="64764-114">*dwLanguageId*</span></span>  
 <span data-ttu-id="64764-115">[Вход] Требуемый язык (LANGID) или значение 0. В последнем случае используется порядок языков Win32 FormatMessage.</span><span class="sxs-lookup"><span data-stu-id="64764-115">[Input] The language desired (LANGID) or 0, in which case the Win32 FormatMessage language order is used.</span></span>  
  
 <span data-ttu-id="64764-116">*wszMessage*</span><span class="sxs-lookup"><span data-stu-id="64764-116">*wszMessage*</span></span>  
 <span data-ttu-id="64764-117">[Выход] Буфер для сохранения сообщения об ошибке LocalDB.</span><span class="sxs-lookup"><span data-stu-id="64764-117">[Output] The buffer to store the LocalDB error message.</span></span>  
  
 <span data-ttu-id="64764-118">*лпкчмессаже*</span><span class="sxs-lookup"><span data-stu-id="64764-118">*lpcchMessage*</span></span>  
 <span data-ttu-id="64764-119">[Вход/выход] На входе содержит размер буфера *wszMessage* в символах.</span><span class="sxs-lookup"><span data-stu-id="64764-119">[Input/Output] On input contains the size of the *wszMessage* buffer in characters.</span></span> <span data-ttu-id="64764-120">На выходе, если указан недостаточный размер буфера, содержит требуемый размер буфера в символах, включая любые конечные символы NULL.</span><span class="sxs-lookup"><span data-stu-id="64764-120">On output, if the given buffer size is too small, contains the buffer size required in characters, including any trailing nulls.</span></span> <span data-ttu-id="64764-121">При успешном завершении работы функции содержит количество символов в сообщении без учета конечных символов NULL.</span><span class="sxs-lookup"><span data-stu-id="64764-121">If the function succeeds, contains the number of characters in the message, excluding any trailing nulls.</span></span>  
  
## <a name="returns"></a><span data-ttu-id="64764-122">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="64764-122">Returns</span></span>  
 <span data-ttu-id="64764-123">S_OK</span><span class="sxs-lookup"><span data-stu-id="64764-123">S_OK</span></span>  
 <span data-ttu-id="64764-124">Функция выполнена успешно.</span><span class="sxs-lookup"><span data-stu-id="64764-124">The function succeeded.</span></span>  
  
 [<span data-ttu-id="64764-125">LOCALDB_ERROR_NOT_INSTALLED</span><span class="sxs-lookup"><span data-stu-id="64764-125">LOCALDB_ERROR_NOT_INSTALLED</span></span>](../express-localdb-error-messages/localdb-error-not-installed.md)  
 <span data-ttu-id="64764-126">Компонент SQL Server Express LocalDB не установлен на компьютере.</span><span class="sxs-lookup"><span data-stu-id="64764-126">SQL Server Express LocalDB is not installed on the computer.</span></span>  
  
 [<span data-ttu-id="64764-127">LOCALDB_ERROR_INVALID_PARAMETER</span><span class="sxs-lookup"><span data-stu-id="64764-127">LOCALDB_ERROR_INVALID_PARAMETER</span></span>](../express-localdb-error-messages/localdb-error-invalid-parameter.md)  
 <span data-ttu-id="64764-128">Один или несколько указанных входных параметров недопустимы.</span><span class="sxs-lookup"><span data-stu-id="64764-128">One or more specified input parameters are invalid.</span></span>  
  
 [<span data-ttu-id="64764-129">LOCALDB_ERROR_UNKNOWN_ERROR_CODE</span><span class="sxs-lookup"><span data-stu-id="64764-129">LOCALDB_ERROR_UNKNOWN_ERROR_CODE</span></span>](../express-localdb-error-messages/localdb-error-unknown-error-code.md)  
 <span data-ttu-id="64764-130">Запрошенное сообщение не существует.</span><span class="sxs-lookup"><span data-stu-id="64764-130">The requested message does not exist.</span></span>  
  
 [<span data-ttu-id="64764-131">LOCALDB_ERROR_UNKNOWN_LANGUAGE_ID</span><span class="sxs-lookup"><span data-stu-id="64764-131">LOCALDB_ERROR_UNKNOWN_LANGUAGE_ID</span></span>](../express-localdb-error-messages/localdb-error-unknown-language-id.md)  
 <span data-ttu-id="64764-132">Сообщение недоступно на запрошенном языке.</span><span class="sxs-lookup"><span data-stu-id="64764-132">The message is not available in the requested language.</span></span>  
  
 [<span data-ttu-id="64764-133">LOCALDB_ERROR_INSUFFICIENT_BUFFER</span><span class="sxs-lookup"><span data-stu-id="64764-133">LOCALDB_ERROR_INSUFFICIENT_BUFFER</span></span>](../express-localdb-error-messages/localdb-error-insufficient-buffer.md)  
 <span data-ttu-id="64764-134">Размер входного буфера *wszMessage* недостаточный; усечение не было запрошено.</span><span class="sxs-lookup"><span data-stu-id="64764-134">The input buffer *wszMessage* is too short, and truncation is not requested.</span></span>  
  
 [<span data-ttu-id="64764-135">LOCALDB_ERROR_INTERNAL_ERROR</span><span class="sxs-lookup"><span data-stu-id="64764-135">LOCALDB_ERROR_INTERNAL_ERROR</span></span>](../express-localdb-error-messages/localdb-error-internal-error.md)  
 <span data-ttu-id="64764-136">Произошла непредвиденная ошибка.</span><span class="sxs-lookup"><span data-stu-id="64764-136">An unexpected error occurred.</span></span> <span data-ttu-id="64764-137">Подробные сведения см. в журнале событий.</span><span class="sxs-lookup"><span data-stu-id="64764-137">See the event log for details.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="64764-138">Remarks</span><span class="sxs-lookup"><span data-stu-id="64764-138">Remarks</span></span>  
 <span data-ttu-id="64764-139">Образец кода, использующего API LocalDB, см. в разделе [SQL Server Express LocalDB Reference](../sql-server-express-localdb-reference.md)</span><span class="sxs-lookup"><span data-stu-id="64764-139">For a code sample that uses LocalDB API, see [SQL Server Express LocalDB Reference](../sql-server-express-localdb-reference.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="64764-140">См. также:</span><span class="sxs-lookup"><span data-stu-id="64764-140">See Also</span></span>  
 [<span data-ttu-id="64764-141">Заголовок и сведения о версии SQL Server Express LocalDB</span><span class="sxs-lookup"><span data-stu-id="64764-141">SQL Server Express LocalDB Header and Version Information</span></span>](sql-server-express-localdb-header-and-version-information.md)  
  
  
