---
title: ISQLServerErrorInfo::GetErrorInfo (OLE DB) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
api_name:
- ISQLServerErrorInfo::GetErrorInfo (OLE DB)
topic_type:
- apiref
helpviewer_keywords:
- GetErrorInfo method
ms.assetid: 83265c9c-eaf9-41f0-9f73-b0ae0972f0d5
author: rothja
ms.author: jroth
ms.openlocfilehash: c3e325cd99276e04a178b89c19b233289edc09fa
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87734062"
---
# <a name="isqlservererrorinfogeterrorinfo-ole-db"></a><span data-ttu-id="46ff6-102">ISQLServerErrorInfo::GetErrorInfo (OLE DB)</span><span class="sxs-lookup"><span data-stu-id="46ff6-102">ISQLServerErrorInfo::GetErrorInfo (OLE DB)</span></span>
  <span data-ttu-id="46ff6-103">Возвращает указатель на [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] собственный клиент OLE DB структуру SSERRORINFO поставщика, содержащую [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] сведения об ошибке.</span><span class="sxs-lookup"><span data-stu-id="46ff6-103">Returns a pointer to a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider SSERRORINFO structure containing the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] error details.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="46ff6-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="46ff6-104">Syntax</span></span>  
  
```  
  
   HRESULT GetErrorInfo(  
SSERRORINFO**ppSSErrorInfo,  
OLECHAR**ppErrorStrings);  
```  
  
## <a name="arguments"></a><span data-ttu-id="46ff6-105">Аргументы</span><span class="sxs-lookup"><span data-stu-id="46ff6-105">Arguments</span></span>  
 <span data-ttu-id="46ff6-106">*ppSSErrorInfo*[out]</span><span class="sxs-lookup"><span data-stu-id="46ff6-106">*ppSSErrorInfo*[out]</span></span>  
 <span data-ttu-id="46ff6-107">Указатель на структуру SSERRORINFO.</span><span class="sxs-lookup"><span data-stu-id="46ff6-107">A pointer to a SSERRORINFO structure.</span></span> <span data-ttu-id="46ff6-108">Если данный метод не дает результатов или отсутствуют сведения [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], связанные с этой ошибкой, поставщик не выделяет памяти и гарантирует, что аргумент *ppSSErrorInfo* при выводе имеет значение NULL.</span><span class="sxs-lookup"><span data-stu-id="46ff6-108">If the method fails or there is no [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] information associated with the error, the provider does not allocate any memory, and ensures that the *ppSSErrorInfo* argument is a null pointer on output.</span></span>  
  
 <span data-ttu-id="46ff6-109">*ppErrorStrings*[out]</span><span class="sxs-lookup"><span data-stu-id="46ff6-109">*ppErrorStrings*[out]</span></span>  
 <span data-ttu-id="46ff6-110">Указатель на Юникод-указатель символьной строки.</span><span class="sxs-lookup"><span data-stu-id="46ff6-110">A pointer to a Unicode character-string pointer.</span></span> <span data-ttu-id="46ff6-111">Если данный метод не дает результатов или отсутствуют сведения [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], связанные с этой ошибкой, поставщик не выделяет памяти и гарантирует, что аргумент *ppErrorStrings* при выводе имеет значение NULL.</span><span class="sxs-lookup"><span data-stu-id="46ff6-111">If the method fails or there is no [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] information associated with an error, the provider does not allocate any memory, and ensures that the *ppErrorStrings* argument is a null pointer on output.</span></span> <span data-ttu-id="46ff6-112">При освобождении аргумента *ppErrorStrings* с помощью метода **IMalloc::Free** высвобождаются три индивидуальных строковых компонента возвращенной структуры SSERRORINFO, так как память выделяется одним блоком.</span><span class="sxs-lookup"><span data-stu-id="46ff6-112">Freeing the *ppErrorStrings* argument with the **IMalloc::Free** method frees the three individual string members of the returned SSERRORINFO structure, as the memory is allocated in a block.</span></span>  
  
## <a name="return-code-values"></a><span data-ttu-id="46ff6-113">Значения кода возврата</span><span class="sxs-lookup"><span data-stu-id="46ff6-113">Return Code Values</span></span>  
 <span data-ttu-id="46ff6-114">S_OK</span><span class="sxs-lookup"><span data-stu-id="46ff6-114">S_OK</span></span>  
 <span data-ttu-id="46ff6-115">Метод выполнен успешно.</span><span class="sxs-lookup"><span data-stu-id="46ff6-115">The method succeeded.</span></span>  
  
 <span data-ttu-id="46ff6-116">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="46ff6-116">E_INVALIDARG</span></span>  
 <span data-ttu-id="46ff6-117">Один из аргументов *ppSSErrorInfo* или *ppErrorStrings* имел значение NULL.</span><span class="sxs-lookup"><span data-stu-id="46ff6-117">Either the *ppSSErrorInfo* or the *ppErrorStrings* argument was NULL.</span></span>  
  
 <span data-ttu-id="46ff6-118">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="46ff6-118">E_OUTOFMEMORY</span></span>  
 <span data-ttu-id="46ff6-119">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]Поставщику OLE DB собственного клиента не удалось выделить достаточно памяти для завершения запроса.</span><span class="sxs-lookup"><span data-stu-id="46ff6-119">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider could not allocate sufficient memory to complete the request.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="46ff6-120">Remarks</span><span class="sxs-lookup"><span data-stu-id="46ff6-120">Remarks</span></span>  
 <span data-ttu-id="46ff6-121">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]Поставщик OLE DB собственного клиента выделяет память для строк SSERRORINFO и олечар, возвращаемых с помощью указателей, переданных потребителем.</span><span class="sxs-lookup"><span data-stu-id="46ff6-121">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider allocates memory for the SSERRORINFO and OLECHAR strings returned through the pointers passed by the consumer.</span></span> <span data-ttu-id="46ff6-122">Пользователь должен освободить эту память с помощью метода **IMalloc::Free**, когда последнему уже не будет требоваться доступ к данным ошибки.</span><span class="sxs-lookup"><span data-stu-id="46ff6-122">The consumer must deallocate this memory by using the **IMalloc::Free** method when it no longer requires access to the error data.</span></span>  
  
 <span data-ttu-id="46ff6-123">Структура SSERRORINFO определена следующим образом.</span><span class="sxs-lookup"><span data-stu-id="46ff6-123">The SSERRORINFO structure is defined as follows:</span></span>  
  
```  
typedef struct tagSSErrorInfo  
   {  
   LPOLESTR pwszMessage;  
   LPOLESTR pwszServer;  
   LPOLESTR pwszProcedure;  
   LONG lNative;  
   BYTE bState;  
   BYTE bClass;  
   WORD wLineNumber;  
   }  
SSERRORINFO;  
```  
  
|<span data-ttu-id="46ff6-124">Член</span><span class="sxs-lookup"><span data-stu-id="46ff6-124">Member</span></span>|<span data-ttu-id="46ff6-125">Описание</span><span class="sxs-lookup"><span data-stu-id="46ff6-125">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="46ff6-126">*pwszMessage*</span><span class="sxs-lookup"><span data-stu-id="46ff6-126">*pwszMessage*</span></span>|<span data-ttu-id="46ff6-127">Сообщение об ошибке [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="46ff6-127">The error message from [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="46ff6-128">Это сообщение возвращается с помощью метода **IErrorInfo::GetDescription**.</span><span class="sxs-lookup"><span data-stu-id="46ff6-128">The message is returned through the **IErrorInfo::GetDescription** method.</span></span>|  
|<span data-ttu-id="46ff6-129">*pwszServer*</span><span class="sxs-lookup"><span data-stu-id="46ff6-129">*pwszServer*</span></span>|<span data-ttu-id="46ff6-130">Имя экземпляра [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], где произошла ошибка.</span><span class="sxs-lookup"><span data-stu-id="46ff6-130">The name of the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] on which the error occurred.</span></span>|  
|<span data-ttu-id="46ff6-131">*pwszProcedure*</span><span class="sxs-lookup"><span data-stu-id="46ff6-131">*pwszProcedure*</span></span>|<span data-ttu-id="46ff6-132">Имя сформировавшей ошибку хранимой процедуры, если эта ошибка произошла в хранимой процедуре; иначе пустая строка.</span><span class="sxs-lookup"><span data-stu-id="46ff6-132">The name of the stored procedure generating the error if the error occurred in a stored procedure; otherwise, an empty string.</span></span>|  
|<span data-ttu-id="46ff6-133">*lNative*</span><span class="sxs-lookup"><span data-stu-id="46ff6-133">*lNative*</span></span>|<span data-ttu-id="46ff6-134">Номер ошибки [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="46ff6-134">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] error number.</span></span> <span data-ttu-id="46ff6-135">Номер ошибки идентичен номеру, возвращаемому в параметре *plNativeError* метода **ISQLErrorInfo::GetSQLInfo**.</span><span class="sxs-lookup"><span data-stu-id="46ff6-135">The error number is identical to that returned in the *plNativeError* parameter of the **ISQLErrorInfo::GetSQLInfo** method.</span></span>|  
|<span data-ttu-id="46ff6-136">*bState*</span><span class="sxs-lookup"><span data-stu-id="46ff6-136">*bState*</span></span>|<span data-ttu-id="46ff6-137">Состояние ошибки [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="46ff6-137">The state of the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] error.</span></span>|  
|<span data-ttu-id="46ff6-138">*bClass*</span><span class="sxs-lookup"><span data-stu-id="46ff6-138">*bClass*</span></span>|<span data-ttu-id="46ff6-139">Степень серьезности ошибки [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="46ff6-139">The severity of the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] error.</span></span>|  
|<span data-ttu-id="46ff6-140">*wLineNumber*</span><span class="sxs-lookup"><span data-stu-id="46ff6-140">*wLineNumber*</span></span>|<span data-ttu-id="46ff6-141">Если это применимо, строка хранимой процедуры [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], которая сформировала сообщение об ошибке.</span><span class="sxs-lookup"><span data-stu-id="46ff6-141">When applicable, the line of a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] stored procedure that generated the error message.</span></span> <span data-ttu-id="46ff6-142">Если ошибка не связана с процедурой, значение по умолчанию составляет 1.</span><span class="sxs-lookup"><span data-stu-id="46ff6-142">If no procedure is involved, the default value is 1.</span></span>|  
  
 <span data-ttu-id="46ff6-143">Указатели в адресах ссылок на структуры в строке, возвращенной в аргументе *ppErrorStrings*.</span><span class="sxs-lookup"><span data-stu-id="46ff6-143">Pointers in the structure reference addresses in the string returned in the *ppErrorStrings* argument.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="46ff6-144">См. также:</span><span class="sxs-lookup"><span data-stu-id="46ff6-144">See Also</span></span>  
 <span data-ttu-id="46ff6-145">[ISQLServerErrorInfo &#40;OLE DB&#41;](../../database-engine/dev-guide/isqlservererrorinfo-ole-db.md) </span><span class="sxs-lookup"><span data-stu-id="46ff6-145">[ISQLServerErrorInfo &#40;OLE DB&#41;](../../database-engine/dev-guide/isqlservererrorinfo-ole-db.md) </span></span>  
 [<span data-ttu-id="46ff6-146">RAISERROR (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="46ff6-146">RAISERROR &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/language-elements/raiserror-transact-sql)  
  
  
