---
title: srv_convert (интерфейс API расширенных хранимых процедур) | Документы Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: stored-procedures
ms.topic: reference
api_name:
- srv_convert
api_location:
- opends60.dll
topic_type:
- apiref
dev_langs:
- C++
helpviewer_keywords:
- srv_convert
ms.assetid: 216b4a31-786e-4361-8a33-e5f6e9790f90
author: rothja
ms.author: jroth
ms.openlocfilehash: 30a0ea356f017ed3d1b3ecc85cf483b4553e120a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87668330"
---
# <a name="srv_convert-extended-stored-procedure-api"></a><span data-ttu-id="4b056-102">srv_convert (API-интерфейс расширенных хранимых процедур)</span><span class="sxs-lookup"><span data-stu-id="4b056-102">srv_convert (Extended Stored Procedure API)</span></span>
    
> [!IMPORTANT]  
>  [!INCLUDE[ssNoteDepFutureDontUse](../../includes/ssnotedepfuturedontuse-md.md)] <span data-ttu-id="4b056-103">Используйте вместо этого интеграцию со средой CLR.</span><span class="sxs-lookup"><span data-stu-id="4b056-103">Use CLR integration instead.</span></span>  
  
 <span data-ttu-id="4b056-104">Преобразует данные из одного типа в другой.</span><span class="sxs-lookup"><span data-stu-id="4b056-104">Changes data from one data type to another.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4b056-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="4b056-105">Syntax</span></span>  
  
```  
  
int srv_convert (  
SRV_PROC *  
srvproc  
,  
int  
srctype  
,  
void *  
src  
,  
DBINT  
srclen  
,  
int  
desttype  
,  
void *  
dest  
,  
DBINT  
destlen  
);  
  
```  
  
## <a name="arguments"></a><span data-ttu-id="4b056-106">Аргументы</span><span class="sxs-lookup"><span data-stu-id="4b056-106">Arguments</span></span>  
 <span data-ttu-id="4b056-107">*srvproc*</span><span class="sxs-lookup"><span data-stu-id="4b056-107">*srvproc*</span></span>  
 <span data-ttu-id="4b056-108">Указатель на структуру SRV_PROC, который представляет собой дескриптор соединения с клиентом.</span><span class="sxs-lookup"><span data-stu-id="4b056-108">Is a pointer to the SRV_PROC structure that is the handle for a particular client connection.</span></span> <span data-ttu-id="4b056-109">В этой структуре содержатся все данные управления, которые используются библиотекой API расширенных хранимых процедур для управления обменом сообщениями и данными между приложением и клиентом.</span><span class="sxs-lookup"><span data-stu-id="4b056-109">The structure contains all the control information that the Extended Stored Procedure API uses to manage communications and data between the application and the client.</span></span> <span data-ttu-id="4b056-110">Если задан дескриптор *srvproc*, он передается функции обработки ошибок из API расширенных хранимых процедур в случае возникновения ошибки.</span><span class="sxs-lookup"><span data-stu-id="4b056-110">If the *srvproc* handle is supplied, it is passed to the Extended Stored Procedure API error handler function when an error occurs.</span></span>  
  
 <span data-ttu-id="4b056-111">*srctype*</span><span class="sxs-lookup"><span data-stu-id="4b056-111">*srctype*</span></span>  
 <span data-ttu-id="4b056-112">Задает тип данных, подлежащих преобразованию.</span><span class="sxs-lookup"><span data-stu-id="4b056-112">Specifies the data type of the data to be converted.</span></span> <span data-ttu-id="4b056-113">Этот параметр может иметь любой из типов данных API-интерфейса расширенных хранимых процедур.</span><span class="sxs-lookup"><span data-stu-id="4b056-113">This parameter can be any of the Extended Store Procedure API data types.</span></span>  
  
 <span data-ttu-id="4b056-114">*src*</span><span class="sxs-lookup"><span data-stu-id="4b056-114">*src*</span></span>  
 <span data-ttu-id="4b056-115">Указатель на данные, подлежащие преобразованию.</span><span class="sxs-lookup"><span data-stu-id="4b056-115">Is a pointer to the data to be converted.</span></span> <span data-ttu-id="4b056-116">Этот параметр может иметь любой из типов данных API-интерфейса расширенных хранимых процедур.</span><span class="sxs-lookup"><span data-stu-id="4b056-116">This parameter can be any of the Extended Store Procedure API data types.</span></span>  
  
 <span data-ttu-id="4b056-117">*srclen*</span><span class="sxs-lookup"><span data-stu-id="4b056-117">*srclen*</span></span>  
 <span data-ttu-id="4b056-118">Задает длину данных, подлежащих преобразованию, в байтах.</span><span class="sxs-lookup"><span data-stu-id="4b056-118">Specifies the length, in bytes, of the data to be converted.</span></span> <span data-ttu-id="4b056-119">Если параметр *srclen* равен 0, то функция **srv_convert** помещает в целевую переменную значение NULL.</span><span class="sxs-lookup"><span data-stu-id="4b056-119">If *srclen* is 0, **srv_convert** places a null value in the destination variable.</span></span> <span data-ttu-id="4b056-120">Если значение этого параметра не равно 0, то он не учитывается для типов данных с фиксированной длиной, для которых исходные данные предполагаются равными NULL.</span><span class="sxs-lookup"><span data-stu-id="4b056-120">Unless it is 0, this parameter is ignored for fixed-length data types, in which case the source data is assumed to be NULL.</span></span> <span data-ttu-id="4b056-121">Для данных типа SRVCHAR длина (равная -1) означает, что строка завершается нулевым символом.</span><span class="sxs-lookup"><span data-stu-id="4b056-121">For data of the SRVCHAR data type, a length of -1 indicates the string is null-terminated.</span></span>  
  
 <span data-ttu-id="4b056-122">*desttype*</span><span class="sxs-lookup"><span data-stu-id="4b056-122">*desttype*</span></span>  
 <span data-ttu-id="4b056-123">Задает тип, к которому будут преобразованы исходные данные.</span><span class="sxs-lookup"><span data-stu-id="4b056-123">Specifies the data type to convert the source to.</span></span> <span data-ttu-id="4b056-124">Этот параметр может иметь любой из типов данных API-интерфейса расширенных хранимых процедур.</span><span class="sxs-lookup"><span data-stu-id="4b056-124">This parameter can be any of the Extended Store Procedure API data types.</span></span>  
  
 <span data-ttu-id="4b056-125">*dest*</span><span class="sxs-lookup"><span data-stu-id="4b056-125">*dest*</span></span>  
 <span data-ttu-id="4b056-126">Указатель на целевую переменную, куда будут помещены преобразованные данные.</span><span class="sxs-lookup"><span data-stu-id="4b056-126">Is a pointer to the destination variable that receives converted data.</span></span> <span data-ttu-id="4b056-127">Если этот указатель имеет значение NULL, функция **srv_convert** вызывает обработчик ошибок, если он был задан пользователем, и возвращает значение –1.</span><span class="sxs-lookup"><span data-stu-id="4b056-127">If this pointer is NULL, **srv_convert** calls the user-supplied error handler ,if any, and returns -1.</span></span>  
  
 <span data-ttu-id="4b056-128">Если значение параметра *desttype* равно SRVDECIMAL или SRVNUMERIC, параметр *dest* должен быть указателем на структуру типа DBNUMERIC или DBDECIMAL с заранее заданными и требуемыми значениями точности и масштаба.</span><span class="sxs-lookup"><span data-stu-id="4b056-128">If *desttype* is SRVDECIMAL or SRVNUMERIC, the *dest* parameter must be a pointer to a DBNUMERIC or DBDECIMAL structure with the precision and scale fields of the structure already set to the desired values.</span></span> <span data-ttu-id="4b056-129">Параметр DEFAULTPRECISION позволяет задать точность по умолчанию, а параметр DEFAULTSCALE — масштаб по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="4b056-129">You can use DEFAULTPRECISION to specify a default precision, and DEFAULTSCALE to specify a default scale.</span></span>  
  
 <span data-ttu-id="4b056-130">*destlen*</span><span class="sxs-lookup"><span data-stu-id="4b056-130">*destlen*</span></span>  
 <span data-ttu-id="4b056-131">Задает длину целевой переменной в байтах.</span><span class="sxs-lookup"><span data-stu-id="4b056-131">Specifies the length, in bytes, of the destination variable.</span></span> <span data-ttu-id="4b056-132">Для типов с фиксированной длиной это значение не учитывается.</span><span class="sxs-lookup"><span data-stu-id="4b056-132">This parameter is ignored for fixed-length data types.</span></span> <span data-ttu-id="4b056-133">Для целевой переменной типа SRVCHAR значение параметра *destlen* представляет собой полную длину буфера назначения.</span><span class="sxs-lookup"><span data-stu-id="4b056-133">For a destination variable of type SRVCHAR, the value of *destlen* must be the total length of the destination buffer space.</span></span> <span data-ttu-id="4b056-134">Длина переменной назначения типа SRVCHAR or SRVBINARY (равная -1) указывает, что места достаточно.</span><span class="sxs-lookup"><span data-stu-id="4b056-134">A length of -1 for a destination variable of type SRVCHAR or SRVBINARY indicates there is sufficient space available.</span></span> <span data-ttu-id="4b056-135">Для переменной назначения типа *srvchar* длина, равная –1, вызывает завершение строки нулевым символом.</span><span class="sxs-lookup"><span data-stu-id="4b056-135">For a destination variable of type *srvchar*, a length of -1 causes the character string to be null-terminated.</span></span>  
  
## <a name="returns"></a><span data-ttu-id="4b056-136">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="4b056-136">Returns</span></span>  
 <span data-ttu-id="4b056-137">Длина преобразованных данных в байтах, если преобразование типов было проведено успешно.</span><span class="sxs-lookup"><span data-stu-id="4b056-137">The length of the converted data, in bytes, if the data type conversion succeeds.</span></span> <span data-ttu-id="4b056-138">Если функция **srv_convert** получает запрос на преобразование, которое не поддерживается, то вызывает обработчик ошибок, если он был задан разработчиком, устанавливает глобальный номер ошибки и возвращает значение –1.</span><span class="sxs-lookup"><span data-stu-id="4b056-138">When **srv_convert** encounters a request for a conversion it does not support, it calls the developer-supplied error handler, if any, sets a global error number, and returns -1.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="4b056-139">Remarks</span><span class="sxs-lookup"><span data-stu-id="4b056-139">Remarks</span></span>  
 <span data-ttu-id="4b056-140">Функция **srv_willconvert** определяет, допустимо ли данное преобразование.</span><span class="sxs-lookup"><span data-stu-id="4b056-140">The **srv_willconvert** function determines whether a particular conversion is allowed.</span></span>  
  
 <span data-ttu-id="4b056-141">Преобразование в приблизительные числовые типы данных SRVFLT4 и SRVFLT8 может привести к некоторой потере точности.</span><span class="sxs-lookup"><span data-stu-id="4b056-141">Converting to the approximate numeric data types SRVFLT4 or SRVFLT8 can result in some loss of precision.</span></span> <span data-ttu-id="4b056-142">Преобразование из приблизительных числовых типов данных SRVFLT4 и SRVFLT8 в типы SRVCHAR и SRVTEXT также может привести к некоторой потере точности.</span><span class="sxs-lookup"><span data-stu-id="4b056-142">Converting from the approximate numeric data types SRVFLT4 or SRVFLT8 to SRVCHAR or SRVTEXT can also result in some loss of precision.</span></span>  
  
 <span data-ttu-id="4b056-143">Преобразование к типу SRVFLT*x*, SRVINT*x*, SRVMONEY, SRVMONEY4, SRVDECIMAL или SRVNUMERIC может привести к переполнению, если число больше максимально допустимого значения для целевого типа, или к потере точности, если число меньше минимально допустимого значения для целевого типа.</span><span class="sxs-lookup"><span data-stu-id="4b056-143">Converting to SRVFLT*x*, SRVINT*x*, SRVMONEY, SRVMONEY4, SRVDECIMAL, or SRVNUMERIC can result in overflow if the number is larger than the maximum value of the destination, or in underflow if the number is smaller than the minimum value of the destination.</span></span> <span data-ttu-id="4b056-144">Если переполнение происходит при преобразовании к типу SRVCHAR или SRVTEXT, то первым символом результирующей величины становится звездочка (\*), свидетельствующая об ошибке.</span><span class="sxs-lookup"><span data-stu-id="4b056-144">If overflow occurs when converting to SRVCHAR or SRVTEXT, the first character of the resulting value contains an asterisk (\*) to indicate the error.</span></span>  
  
 <span data-ttu-id="4b056-145">При преобразовании SRVCHAR в SRVBINARY функция **srv_convert** интерпретирует SRVCHAR как шестнадцатеричное значение, независимо от того, начинается ли строка с 0.</span><span class="sxs-lookup"><span data-stu-id="4b056-145">When converting SRVCHAR to SRVBINARY, **srv_convert** interprets SRVCHAR as hexadecimal, whether or not the string contains a leading 0.</span></span> <span data-ttu-id="4b056-146">При преобразовании SRVBINARY в SRVCHAR функция **srv_convert** создает шестнадцатеричную строку без начального 0.</span><span class="sxs-lookup"><span data-stu-id="4b056-146">When converting SRVBINARY to SRVCHAR, **srv_convert** creates a hexadecimal string without a leading 0.</span></span> <span data-ttu-id="4b056-147">Во всех остальных случаях преобразование в тип данных SRVBINARY и обратно — прямое побитовое копирование.</span><span class="sxs-lookup"><span data-stu-id="4b056-147">In all other cases, a conversion to or from the SRVBINARY data type is a straight bit-copy.</span></span>  
  
 <span data-ttu-id="4b056-148">В некоторых случаях применяется преобразование значений некоторого типа в значения того же типа.</span><span class="sxs-lookup"><span data-stu-id="4b056-148">In certain cases, it can be useful to convert a data type to itself.</span></span> <span data-ttu-id="4b056-149">Например, преобразование из типа SRVCHAR в тип SRVCHAR с параметром *destlen* (равным –1) добавляет к строке признак конца в виде нулевого символа.</span><span class="sxs-lookup"><span data-stu-id="4b056-149">For example, converting SRVCHAR to SRVCHAR with a *destlen* of -1 adds a null terminator to a string.</span></span>  
  
 <span data-ttu-id="4b056-150">Описание типов данных и преобразований типов данных API-интерфейса расширенных хранимых процедур см. в разделе [Типы данных (интерфейс API расширенных хранимых процедур)](data-types-extended-stored-procedure-api.md).</span><span class="sxs-lookup"><span data-stu-id="4b056-150">For a description of data types and Extended Store Procedure API data type conversions, see [Data Types &#40;Extended Stored Procedure API&#41;](data-types-extended-stored-procedure-api.md).</span></span>  
  
 <span data-ttu-id="4b056-151">Вызов функции **srv_convert** может оказаться неудачным по нескольким причинам.</span><span class="sxs-lookup"><span data-stu-id="4b056-151">The **srv_convert** function can fail for several reasons:</span></span>  
  
-   <span data-ttu-id="4b056-152">Запрошенное преобразование невозможно.</span><span class="sxs-lookup"><span data-stu-id="4b056-152">The requested conversion is not available.</span></span>  
  
-   <span data-ttu-id="4b056-153">Преобразование привело к усечению, переполнению или потере точности в целевой переменной.</span><span class="sxs-lookup"><span data-stu-id="4b056-153">The conversion resulted in truncation, overflow, or loss of precision in the destination variable.</span></span>  
  
-   <span data-ttu-id="4b056-154">При преобразовании строки символов в числовой тип произошла синтаксическая ошибка.</span><span class="sxs-lookup"><span data-stu-id="4b056-154">A syntax error occurred while converting a character string to a numeric data type.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="4b056-155">Необходимо тщательно просмотреть исходный код расширенных хранимых процедур и проверить скомпилированные библиотеки DLL перед их установкой на рабочий сервер.</span><span class="sxs-lookup"><span data-stu-id="4b056-155">You should thoroughly review the source code of extended stored procedures, and you should test the compiled DLLs before you install them on a production server.</span></span> <span data-ttu-id="4b056-156">Сведения о проверке безопасности см. на следующем [веб-сайте Майкрософт](https://go.microsoft.com/fwlink/?LinkID=54761&amp;clcid=0x409https://msdn.microsoft.com/security/).</span><span class="sxs-lookup"><span data-stu-id="4b056-156">For information about security review and testing, see this [Microsoft Web site](https://go.microsoft.com/fwlink/?LinkID=54761&amp;clcid=0x409https://msdn.microsoft.com/security/).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4b056-157">См. также:</span><span class="sxs-lookup"><span data-stu-id="4b056-157">See Also</span></span>  
 <span data-ttu-id="4b056-158">[API srv_setutype &#40;расширенных хранимых процедур&#41;](srv-setutype-extended-stored-procedure-api.md) </span><span class="sxs-lookup"><span data-stu-id="4b056-158">[srv_setutype &#40;Extended Stored Procedure API&#41;](srv-setutype-extended-stored-procedure-api.md) </span></span>  
 [<span data-ttu-id="4b056-159">srv_willconvert (интерфейс API расширенных хранимых процедур)</span><span class="sxs-lookup"><span data-stu-id="4b056-159">srv_willconvert &#40;Extended Stored Procedure API&#41;</span></span>](srv-willconvert-extended-stored-procedure-api.md)  
  
  
