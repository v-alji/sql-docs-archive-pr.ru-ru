---
title: srv_describe (интерфейс API расширенных хранимых процедур) | Документы Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: stored-procedures
ms.topic: reference
api_name:
- srv_describe
api_location:
- opends60.dll
topic_type:
- apiref
dev_langs:
- C++
helpviewer_keywords:
- srv_describe
ms.assetid: 2115600e-5ce7-4be0-9cd3-a1dd1fab0729
author: rothja
ms.author: jroth
ms.openlocfilehash: 52a397b79f4fcecaa2ccacde7500cb852ae793fd
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87668329"
---
# <a name="srv_describe-extended-stored-procedure-api"></a><span data-ttu-id="fbfb2-102">srv_describe (API-интерфейс расширенных хранимых процедур)</span><span class="sxs-lookup"><span data-stu-id="fbfb2-102">srv_describe (Extended Stored Procedure API)</span></span>
    
> [!IMPORTANT]  
>  [!INCLUDE[ssNoteDepFutureDontUse](../../includes/ssnotedepfuturedontuse-md.md)] <span data-ttu-id="fbfb2-103">Используйте вместо этого интеграцию со средой CLR.</span><span class="sxs-lookup"><span data-stu-id="fbfb2-103">Use CLR integration instead.</span></span>  
  
 <span data-ttu-id="fbfb2-104">Задает имя столбца, исходный и целевой типы данных для конкретного столбца в строке.</span><span class="sxs-lookup"><span data-stu-id="fbfb2-104">Defines the column name and source and destination data types for a specific column in a row.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fbfb2-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="fbfb2-105">Syntax</span></span>  
  
```  
  
int srv_describe (  
SRV_PROC *  
srvproc  
,  
int  
colnumber  
,  
DBCHAR *  
column_name  
,  
int  
namelen  
,  
DBINT  
desttype  
,  
DBINT  
destlen  
,  
DBINT  
srctype  
,  
DBINT  
srclen  
,  
void *  
srcdata  
);  
  
```  
  
## <a name="arguments"></a><span data-ttu-id="fbfb2-106">Аргументы</span><span class="sxs-lookup"><span data-stu-id="fbfb2-106">Arguments</span></span>  
 <span data-ttu-id="fbfb2-107">*srvproc*</span><span class="sxs-lookup"><span data-stu-id="fbfb2-107">*srvproc*</span></span>  
 <span data-ttu-id="fbfb2-108">Указатель на структуру SRV_PROC, который представляет собой дескриптор для конкретного клиентского соединения (в данном случае подразумевается клиент, который отправил строку).</span><span class="sxs-lookup"><span data-stu-id="fbfb2-108">Is a pointer to the SRV_PROC structure that is the handle for a particular client connection (in this case, the client sending the row).</span></span> <span data-ttu-id="fbfb2-109">В этой структуре содержатся все сведения, которые библиотека API-интерфейса расширенных хранимых процедур использует для управления обменом данными между приложением и клиентом.</span><span class="sxs-lookup"><span data-stu-id="fbfb2-109">The structure contains all the information that the Extended Stored Procedure API library uses to manage communications and data between the application and the client.</span></span>  
  
 <span data-ttu-id="fbfb2-110">*colnumber*</span><span class="sxs-lookup"><span data-stu-id="fbfb2-110">*colnumber*</span></span>  
 <span data-ttu-id="fbfb2-111">Не поддерживается в текущей версии.</span><span class="sxs-lookup"><span data-stu-id="fbfb2-111">Is currently not supported.</span></span> <span data-ttu-id="fbfb2-112">Столбцы должны быть описаны по порядку.</span><span class="sxs-lookup"><span data-stu-id="fbfb2-112">Columns must be described in order.</span></span> <span data-ttu-id="fbfb2-113">Все столбцы должны быть описаны до вызова **srv_sendrow**.</span><span class="sxs-lookup"><span data-stu-id="fbfb2-113">All columns must be described before **srv_sendrow** is called.</span></span>  
  
 <span data-ttu-id="fbfb2-114">*column_name*</span><span class="sxs-lookup"><span data-stu-id="fbfb2-114">*column_name*</span></span>  
 <span data-ttu-id="fbfb2-115">Задает имя столбца, к которому принадлежат данные.</span><span class="sxs-lookup"><span data-stu-id="fbfb2-115">Specifies the name of the column to which the data belongs.</span></span> <span data-ttu-id="fbfb2-116">Этот параметр может иметь значение NULL, поскольку столбец не обязательно должен иметь имя.</span><span class="sxs-lookup"><span data-stu-id="fbfb2-116">This parameter can be NULL because a column is not required to have a name.</span></span>  
  
 <span data-ttu-id="fbfb2-117">*namelen*</span><span class="sxs-lookup"><span data-stu-id="fbfb2-117">*namelen*</span></span>  
 <span data-ttu-id="fbfb2-118">Задает длину *column_name* в байтах.</span><span class="sxs-lookup"><span data-stu-id="fbfb2-118">Specifies the length, in bytes, of *column_name*.</span></span> <span data-ttu-id="fbfb2-119">Если значение аргумента *namelen* равно SRV_NULLTERM, то значение аргумента *column_name* должно оканчиваться нулевым символом.</span><span class="sxs-lookup"><span data-stu-id="fbfb2-119">If *namelen* is SRV_NULLTERM, then *column_name* must be null-terminated.</span></span>  
  
 <span data-ttu-id="fbfb2-120">*desttype*</span><span class="sxs-lookup"><span data-stu-id="fbfb2-120">*desttype*</span></span>  
 <span data-ttu-id="fbfb2-121">Задает тип данных столбца строки назначения.</span><span class="sxs-lookup"><span data-stu-id="fbfb2-121">Specifies the data type of the destination row column.</span></span> <span data-ttu-id="fbfb2-122">Это — тип данных, передаваемых клиенту.</span><span class="sxs-lookup"><span data-stu-id="fbfb2-122">This is the data type sent to the client.</span></span> <span data-ttu-id="fbfb2-123">Тип данных нужно задавать, даже если данные имеют значение NULL. Дополнительные сведения см. в разделе [Типы данных (интерфейс API расширенных хранимых процедур)](data-types-extended-stored-procedure-api.md).</span><span class="sxs-lookup"><span data-stu-id="fbfb2-123">The data type must be specified even if the data is NULL, for more information, see [Data Types &#40;Extended Stored Procedure API&#41;](data-types-extended-stored-procedure-api.md).</span></span>  
  
 <span data-ttu-id="fbfb2-124">*destlen*</span><span class="sxs-lookup"><span data-stu-id="fbfb2-124">*destlen*</span></span>  
 <span data-ttu-id="fbfb2-125">Задает длину данных (в байтах), которые должны быть переданы клиенту.</span><span class="sxs-lookup"><span data-stu-id="fbfb2-125">Specifies the length, in bytes, of the data to be sent to the client.</span></span> <span data-ttu-id="fbfb2-126">Для типов данных фиксированной длины, не допускающих значений NULL, параметр *destlen* не учитывается.</span><span class="sxs-lookup"><span data-stu-id="fbfb2-126">For fixed-length data types that do not allow null values, *destlen* is ignored.</span></span> <span data-ttu-id="fbfb2-127">Для типов данных с переменной длиной и типов данных с фиксированной длиной, поддерживающих значения NULL, параметр *destlen* задает максимальную длину целевых данных.</span><span class="sxs-lookup"><span data-stu-id="fbfb2-127">For variable-length data types and fixed-length data types that allow null values, *destlen* specifies the maximum length the destination data can be.</span></span>  
  
 <span data-ttu-id="fbfb2-128">*srctype*</span><span class="sxs-lookup"><span data-stu-id="fbfb2-128">*srctype*</span></span>  
 <span data-ttu-id="fbfb2-129">Задает тип исходных данных.</span><span class="sxs-lookup"><span data-stu-id="fbfb2-129">Specifies the data type of the source data.</span></span>  
  
 <span data-ttu-id="fbfb2-130">*srclen*</span><span class="sxs-lookup"><span data-stu-id="fbfb2-130">*srclen*</span></span>  
 <span data-ttu-id="fbfb2-131">Задает длину исходных данных в байтах.</span><span class="sxs-lookup"><span data-stu-id="fbfb2-131">Specifies the length, in bytes, of the source data.</span></span> <span data-ttu-id="fbfb2-132">Для типов данных с фиксированной длиной это значение не учитывается.</span><span class="sxs-lookup"><span data-stu-id="fbfb2-132">This value is ignored for fixed-length data types.</span></span>  
  
 <span data-ttu-id="fbfb2-133">*srcdata*</span><span class="sxs-lookup"><span data-stu-id="fbfb2-133">*srcdata*</span></span>  
 <span data-ttu-id="fbfb2-134">Предоставляет адрес исходных данных для конкретного столбца.</span><span class="sxs-lookup"><span data-stu-id="fbfb2-134">Provides the source data address for a particular column.</span></span> <span data-ttu-id="fbfb2-135">Функция **srv_sendrow** после вызова ищет данные для параметра *colnumber* в параметре *srcdata*.</span><span class="sxs-lookup"><span data-stu-id="fbfb2-135">When **srv_sendrow** is called, it looks for the data for *colnumber* at *srcdata*.</span></span> <span data-ttu-id="fbfb2-136">Следовательно, этот параметр нельзя освобождать до вызова функции **srv_sendrow**.</span><span class="sxs-lookup"><span data-stu-id="fbfb2-136">Therefore it should not be freed before a call to **srv_sendrow**.</span></span> <span data-ttu-id="fbfb2-137">Адрес исходных данных можно изменить между вызовами функции **srv_sendrow** с помощью вызова функции **srv_setcoldata**.</span><span class="sxs-lookup"><span data-stu-id="fbfb2-137">The source data address can be changed between calls to **srv_sendrow** by using **srv_setcoldata**.</span></span> <span data-ttu-id="fbfb2-138">Память, выделенная для *srcdata*, не должна освобождаться до замены данных столбца с помощью еще одного вызова метода **srv_setcoldata** или **srv_senddone**.</span><span class="sxs-lookup"><span data-stu-id="fbfb2-138">Memory allocated for *srcdata* should not be freed until the column data is replaced by another call to **srv_setcoldata**, or until **srv_senddone** is called.</span></span>  
  
 <span data-ttu-id="fbfb2-139">Если значение параметра *desttype* равно SRVDECIMAL или SRVNUMERIC, параметр *srcdata* должен быть указателем на структуру типа DBNUMERIC или DBDECIMAL, в которой полям точности и масштаба уже присвоены требуемые значения.</span><span class="sxs-lookup"><span data-stu-id="fbfb2-139">If *desttype* is SRVDECIMAL or SRVNUMERIC, the *srcdata* parameter must be a pointer to a DBNUMERIC or DBDECIMAL structure with the precision and scale fields of the structure already set to the values you want.</span></span> <span data-ttu-id="fbfb2-140">Параметр DEFAULTPRECISION позволяет задать точность по умолчанию, а параметр DEFAULTSCALE — масштаб по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="fbfb2-140">You can use DEFAULTPRECISION to specify a default precision, and DEFAULTSCALE to specify a default scale.</span></span>  
  
## <a name="returns"></a><span data-ttu-id="fbfb2-141">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="fbfb2-141">Returns</span></span>  
 <span data-ttu-id="fbfb2-142">Порядковый номер описываемого столбца.</span><span class="sxs-lookup"><span data-stu-id="fbfb2-142">The number of the column described.</span></span> <span data-ttu-id="fbfb2-143">Первый столбец имеет номер 1.</span><span class="sxs-lookup"><span data-stu-id="fbfb2-143">The first column is column 1.</span></span> <span data-ttu-id="fbfb2-144">При возникновении ошибки возвращается 0.</span><span class="sxs-lookup"><span data-stu-id="fbfb2-144">If an error occurs, returns 0.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="fbfb2-145">Remarks</span><span class="sxs-lookup"><span data-stu-id="fbfb2-145">Remarks</span></span>  
 <span data-ttu-id="fbfb2-146">Функция **srv_describe** должна быть вызвана по одному разу для каждого столбца данной строки перед первым вызовом функции **srv_sendrow**.</span><span class="sxs-lookup"><span data-stu-id="fbfb2-146">The **srv_describe** function must be called once for each column in the row before the first call to **srv_sendrow**.</span></span> <span data-ttu-id="fbfb2-147">Столбцы в строке могут быть описаны в любом порядке.</span><span class="sxs-lookup"><span data-stu-id="fbfb2-147">The columns of a row can be described in any order.</span></span>  
  
 <span data-ttu-id="fbfb2-148">Для изменения местонахождения и длины исходных данных в строках столбцов до передачи полного результирующего набора можно использовать функции **srv_setcoldata** и **srv_setcollen**, соответственно.</span><span class="sxs-lookup"><span data-stu-id="fbfb2-148">To change the location and length of the source data in column rows before the complete result set has been sent, use **srv_setcoldata** and **srv_setcollen**, respectively.</span></span>  
  
 <span data-ttu-id="fbfb2-149">Описание типов данных и преобразований типов данных API-интерфейса расширенных хранимых процедур см. в разделе [Типы данных (интерфейс API расширенных хранимых процедур)](data-types-extended-stored-procedure-api.md).</span><span class="sxs-lookup"><span data-stu-id="fbfb2-149">For a description of data types and Extended Store Procedure API data type conversions, see[Data Types &#40;Extended Stored Procedure API&#41;](data-types-extended-stored-procedure-api.md).</span></span>  
  
 <span data-ttu-id="fbfb2-150">Если имя столбца в приложении задано в Юникоде, то перед вызовом функции **srv_describe** его нужно перевести в многобайтовую кодировку, заданную на сервере.</span><span class="sxs-lookup"><span data-stu-id="fbfb2-150">If the column name in your application is in Unicode, you need to convert it to the multibyte code page of the server before calling **srv_describe**.</span></span> <span data-ttu-id="fbfb2-151">Дополнительные сведения см. в статье [данные в Юникоде и серверные кодовые страницы](../extended-stored-procedures-programming/unicode-data-and-server-code-pages.md).</span><span class="sxs-lookup"><span data-stu-id="fbfb2-151">For more information, see [Unicode Data and Server Code Pages](../extended-stored-procedures-programming/unicode-data-and-server-code-pages.md).</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="fbfb2-152">Необходимо тщательно просмотреть исходный код расширенных хранимых процедур и проверить скомпилированные библиотеки DLL перед их установкой на рабочий сервер.</span><span class="sxs-lookup"><span data-stu-id="fbfb2-152">You should thoroughly review the source code of extended stored procedures, and you should test the compiled DLLs before you install them on a production server.</span></span> <span data-ttu-id="fbfb2-153">Сведения о проверке безопасности см. на следующем [веб-сайте Майкрософт](https://go.microsoft.com/fwlink/?LinkID=54761&amp;clcid=0x409https://msdn.microsoft.com/security/).</span><span class="sxs-lookup"><span data-stu-id="fbfb2-153">For information about security review and testing, see this [Microsoft Web site](https://go.microsoft.com/fwlink/?LinkID=54761&amp;clcid=0x409https://msdn.microsoft.com/security/).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fbfb2-154">См. также:</span><span class="sxs-lookup"><span data-stu-id="fbfb2-154">See Also</span></span>  
 <span data-ttu-id="fbfb2-155">[API srv_sendrow &#40;расширенных хранимых процедур&#41;](srv-sendrow-extended-stored-procedure-api.md) </span><span class="sxs-lookup"><span data-stu-id="fbfb2-155">[srv_sendrow &#40;Extended Stored Procedure API&#41;](srv-sendrow-extended-stored-procedure-api.md) </span></span>  
 <span data-ttu-id="fbfb2-156">[API srv_setutype &#40;расширенных хранимых процедур&#41;](srv-setutype-extended-stored-procedure-api.md) </span><span class="sxs-lookup"><span data-stu-id="fbfb2-156">[srv_setutype &#40;Extended Stored Procedure API&#41;](srv-setutype-extended-stored-procedure-api.md) </span></span>  
 [<span data-ttu-id="fbfb2-157">srv_setcoldata (интерфейс API расширенных хранимых процедур)</span><span class="sxs-lookup"><span data-stu-id="fbfb2-157">srv_setcoldata &#40;Extended Stored Procedure API&#41;</span></span>](srv-setcoldata-extended-stored-procedure-api.md)  
  
  
