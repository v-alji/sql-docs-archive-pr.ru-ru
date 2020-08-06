---
title: srv_paramlen (интерфейс API расширенных хранимых процедур) | Документы Майкрософт
ms.custom: ''
ms.date: 03/08/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: stored-procedures
ms.topic: reference
api_name:
- srv_paramlen
api_location:
- opends60.dll
topic_type:
- apiref
dev_langs:
- C++
helpviewer_keywords:
- srv_paramlen
ms.assetid: d1fe92ff-cad6-4396-8216-125e5642e81e
author: rothja
ms.author: jroth
ms.openlocfilehash: fc2a0fa7f8409767a2afaa9c4c621ea72732b701
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87751028"
---
# <a name="srv_paramlen-extended-stored-procedure-api"></a><span data-ttu-id="24205-102">srv_paramlen (API-интерфейс расширенных хранимых процедур)</span><span class="sxs-lookup"><span data-stu-id="24205-102">srv_paramlen (Extended Stored Procedure API)</span></span>
    
> [!IMPORTANT]  
>  [!INCLUDE[ssNoteDepFutureDontUse](../../includes/ssnotedepfuturedontuse-md.md)] <span data-ttu-id="24205-103">Используйте вместо этого интеграцию со средой CLR.</span><span class="sxs-lookup"><span data-stu-id="24205-103">Use CLR integration instead.</span></span>  
  
 <span data-ttu-id="24205-104">Возвращает длину данных параметра вызова удаленной хранимой процедуры.</span><span class="sxs-lookup"><span data-stu-id="24205-104">Returns the data length of a remote stored procedure call parameter.</span></span> <span data-ttu-id="24205-105">Эта функция заменена функцией **srv_paraminfo**.</span><span class="sxs-lookup"><span data-stu-id="24205-105">This function has been superseded by the **srv_paraminfo** function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="24205-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="24205-106">Syntax</span></span>  
  
```  
  
int srv_paramlen (  
SRV_PROC *  
srvproc  
,  
int  
n   
);  
  
```  
  
## <a name="arguments"></a><span data-ttu-id="24205-107">Аргументы</span><span class="sxs-lookup"><span data-stu-id="24205-107">Arguments</span></span>  
 <span data-ttu-id="24205-108">*srvproc*</span><span class="sxs-lookup"><span data-stu-id="24205-108">*srvproc*</span></span>  
 <span data-ttu-id="24205-109">Указатель на структуру SRV_PROC, представляющую собой дескриптор соединения с клиентом (в данном случае — дескриптор, который получил вызов удаленной хранимой процедуры).</span><span class="sxs-lookup"><span data-stu-id="24205-109">Is a pointer to the SRV_PROC structure that is the handle for a particular client connection (in this case, the handle that received the remote stored procedure call).</span></span> <span data-ttu-id="24205-110">Структура содержит сведения, которые используются библиотекой API-интерфейса расширенных хранимых процедур для управления связью и передачи данных между приложением и клиентом.</span><span class="sxs-lookup"><span data-stu-id="24205-110">The structure contains information that the Extended Stored Procedure API library uses to manage communication and data between the application and the client.</span></span>  
  
 <span data-ttu-id="24205-111">*n*</span><span class="sxs-lookup"><span data-stu-id="24205-111">*n*</span></span>  
 <span data-ttu-id="24205-112">Указывает номер параметра.</span><span class="sxs-lookup"><span data-stu-id="24205-112">Indicates the number of the parameter.</span></span> <span data-ttu-id="24205-113">Первый параметр имеет значение 1.</span><span class="sxs-lookup"><span data-stu-id="24205-113">The first parameter is 1.</span></span>  
  
## <a name="returns"></a><span data-ttu-id="24205-114">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="24205-114">Returns</span></span>  
 <span data-ttu-id="24205-115">Фактическая длина данных параметра в байтах.</span><span class="sxs-lookup"><span data-stu-id="24205-115">The actual length, in bytes, of the parameter data.</span></span> <span data-ttu-id="24205-116">Если параметра с номером *n* или удаленной хранимой процедуры не существует, возвращается значение -1.</span><span class="sxs-lookup"><span data-stu-id="24205-116">If there is no *n*th parameter or there is no remote stored procedure, it returns -1.</span></span> <span data-ttu-id="24205-117">Если параметр с номером *n* имеет значение NULL, то возвращается 0.</span><span class="sxs-lookup"><span data-stu-id="24205-117">If the *n*th parameter is NULL, it returns 0.</span></span>  
  
 <span data-ttu-id="24205-118">Эта функция возвращает следующие значения, если параметр является одним из следующих [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] системных типов данных.</span><span class="sxs-lookup"><span data-stu-id="24205-118">This function returns the following values, if the parameter is one of the following [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] system data types.</span></span>  
  
|<span data-ttu-id="24205-119">Новые типы данных</span><span class="sxs-lookup"><span data-stu-id="24205-119">New data types</span></span>|<span data-ttu-id="24205-120">Длина входных данных</span><span class="sxs-lookup"><span data-stu-id="24205-120">Input data length</span></span>|  
|--------------------|-----------------------|  
|`BITN`|<span data-ttu-id="24205-121">**NULL:** 1</span><span class="sxs-lookup"><span data-stu-id="24205-121">**NULL:** 1</span></span><br /><br /> <span data-ttu-id="24205-122">**Ноль:** 1</span><span class="sxs-lookup"><span data-stu-id="24205-122">**ZERO:** 1</span></span><br /><br /> <span data-ttu-id="24205-123">**>= 255:** Н/Д</span><span class="sxs-lookup"><span data-stu-id="24205-123">**>=255:** N/A</span></span><br /><br /> <span data-ttu-id="24205-124">**<255:** Н/Д</span><span class="sxs-lookup"><span data-stu-id="24205-124">**<255:** N/A</span></span>|  
|`BIGVARCHAR`|<span data-ttu-id="24205-125">**NULL:** 0</span><span class="sxs-lookup"><span data-stu-id="24205-125">**NULL:** 0</span></span><br /><br /> <span data-ttu-id="24205-126">**Ноль:** 1</span><span class="sxs-lookup"><span data-stu-id="24205-126">**ZERO:** 1</span></span><br /><br /> <span data-ttu-id="24205-127">**>= 255:** 255</span><span class="sxs-lookup"><span data-stu-id="24205-127">**>=255:** 255</span></span><br /><br /> <span data-ttu-id="24205-128">**<255:** фактическое значение *len*</span><span class="sxs-lookup"><span data-stu-id="24205-128">**<255:** actual *len*</span></span>|  
|`BIGCHAR`|<span data-ttu-id="24205-129">**NULL:** 0</span><span class="sxs-lookup"><span data-stu-id="24205-129">**NULL:** 0</span></span><br /><br /> <span data-ttu-id="24205-130">**ZERO:** 255</span><span class="sxs-lookup"><span data-stu-id="24205-130">**ZERO:** 255</span></span><br /><br /> <span data-ttu-id="24205-131">**>= 255:** 255</span><span class="sxs-lookup"><span data-stu-id="24205-131">**>=255:** 255</span></span><br /><br /> <span data-ttu-id="24205-132">**<255:** 255</span><span class="sxs-lookup"><span data-stu-id="24205-132">**<255:** 255</span></span>|  
|`BIGBINARY`|<span data-ttu-id="24205-133">**NULL:** 0</span><span class="sxs-lookup"><span data-stu-id="24205-133">**NULL:** 0</span></span><br /><br /> <span data-ttu-id="24205-134">**ZERO:** 255</span><span class="sxs-lookup"><span data-stu-id="24205-134">**ZERO:** 255</span></span><br /><br /> <span data-ttu-id="24205-135">**>= 255:** 255</span><span class="sxs-lookup"><span data-stu-id="24205-135">**>=255:** 255</span></span><br /><br /> <span data-ttu-id="24205-136">**<255:** 255</span><span class="sxs-lookup"><span data-stu-id="24205-136">**<255:** 255</span></span>|  
|`BIGVARBINARY`|<span data-ttu-id="24205-137">**NULL:** 0</span><span class="sxs-lookup"><span data-stu-id="24205-137">**NULL:** 0</span></span><br /><br /> <span data-ttu-id="24205-138">**Ноль:** 1</span><span class="sxs-lookup"><span data-stu-id="24205-138">**ZERO:** 1</span></span><br /><br /> <span data-ttu-id="24205-139">**>= 255:** 255</span><span class="sxs-lookup"><span data-stu-id="24205-139">**>=255:** 255</span></span><br /><br /> <span data-ttu-id="24205-140">**<255:** фактическое значение *len*</span><span class="sxs-lookup"><span data-stu-id="24205-140">**<255:** actual *len*</span></span>|  
|`NCHAR`|<span data-ttu-id="24205-141">**NULL:** 0</span><span class="sxs-lookup"><span data-stu-id="24205-141">**NULL:** 0</span></span><br /><br /> <span data-ttu-id="24205-142">**ZERO:** 255</span><span class="sxs-lookup"><span data-stu-id="24205-142">**ZERO:** 255</span></span><br /><br /> <span data-ttu-id="24205-143">**>= 255:** 255</span><span class="sxs-lookup"><span data-stu-id="24205-143">**>=255:** 255</span></span><br /><br /> <span data-ttu-id="24205-144">**<255:** 255</span><span class="sxs-lookup"><span data-stu-id="24205-144">**<255:** 255</span></span>|  
|`NVARCHAR`|<span data-ttu-id="24205-145">**NULL:** 0</span><span class="sxs-lookup"><span data-stu-id="24205-145">**NULL:** 0</span></span><br /><br /> <span data-ttu-id="24205-146">**Ноль:** 1</span><span class="sxs-lookup"><span data-stu-id="24205-146">**ZERO:** 1</span></span><br /><br /> <span data-ttu-id="24205-147">**>= 255:** 255</span><span class="sxs-lookup"><span data-stu-id="24205-147">**>=255:** 255</span></span><br /><br /> <span data-ttu-id="24205-148">**<255:** фактическое значение *len*</span><span class="sxs-lookup"><span data-stu-id="24205-148">**<255:** actual *len*</span></span>|  
|`NTEXT`|<span data-ttu-id="24205-149">**Null:** -1</span><span class="sxs-lookup"><span data-stu-id="24205-149">**NULL:** -1</span></span><br /><br /> <span data-ttu-id="24205-150">**ZERO:** –1</span><span class="sxs-lookup"><span data-stu-id="24205-150">**ZERO:** -1</span></span><br /><br /> <span data-ttu-id="24205-151">**>= 255:** -1</span><span class="sxs-lookup"><span data-stu-id="24205-151">**>=255:** -1</span></span><br /><br /> <span data-ttu-id="24205-152">**<255:** -1</span><span class="sxs-lookup"><span data-stu-id="24205-152">**<255:** -1</span></span>|  
  
 <span data-ttu-id="24205-153">\* фактическое значение *len* = длина многобайтовой символьной строки (cch)</span><span class="sxs-lookup"><span data-stu-id="24205-153">\*   actual *len* = Length of multibyte character string (cch)</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="24205-154">Remarks</span><span class="sxs-lookup"><span data-stu-id="24205-154">Remarks</span></span>  
 <span data-ttu-id="24205-155">У каждого параметра удаленной хранимой процедуры есть максимальная и реальная длина данных.</span><span class="sxs-lookup"><span data-stu-id="24205-155">Each remote stored procedure parameter has an actual and a maximum data length.</span></span> <span data-ttu-id="24205-156">Для стандартных типов данных с фиксированной длиной, которые не поддерживают значений NULL, реальная и максимальная длина одинаковы.</span><span class="sxs-lookup"><span data-stu-id="24205-156">For standard fixed-length data types that do not allow null values, the actual and maximum lengths are the same.</span></span> <span data-ttu-id="24205-157">У типов данных переменной длины эти длины могут быть разными.</span><span class="sxs-lookup"><span data-stu-id="24205-157">For variable-length data types, the lengths can vary.</span></span> <span data-ttu-id="24205-158">Например, параметр, объявленный как `varchar(30)`, может иметь данные длиной всего 10 байт.</span><span class="sxs-lookup"><span data-stu-id="24205-158">For example, a parameter declared as `varchar(30)` can have data that is only 10 bytes long.</span></span> <span data-ttu-id="24205-159">Фактическая длина параметра — 10, а максимальная — 30.</span><span class="sxs-lookup"><span data-stu-id="24205-159">The parameter's actual length is 10 and its maximum length is 30.</span></span> <span data-ttu-id="24205-160">Функция **srv_paramlen** возвращает фактическую длину данных в байтах удаленной хранимой процедуры.</span><span class="sxs-lookup"><span data-stu-id="24205-160">The **srv_paramlen** function gets the actual data length, in bytes, of a remote stored procedure.</span></span> <span data-ttu-id="24205-161">Для получения максимальной длины данных параметра используется функция **srv_parammaxlen**.</span><span class="sxs-lookup"><span data-stu-id="24205-161">To obtain the maximum data length of a parameter, use **srv_parammaxlen**.</span></span>  
  
 <span data-ttu-id="24205-162">Когда удаленная хранимая процедура вызывается с параметрами, эти параметры могут быть переданы либо по имени, либо по позиции — без указания имени.</span><span class="sxs-lookup"><span data-stu-id="24205-162">When a remote stored procedure call is made with parameters, the parameters can be passed either by name or by position (unnamed).</span></span> <span data-ttu-id="24205-163">Если при вызове удаленной хранимой процедуры часть параметров передается по имени, а часть — по позиции, возникает ошибка.</span><span class="sxs-lookup"><span data-stu-id="24205-163">If the remote stored procedure call is made with some parameters passed by name and some passed by position, an error occurs.</span></span> <span data-ttu-id="24205-164">Обработчик SRV_RPC по-прежнему вызывается, но он выглядит так, как если бы параметры не существовали, а **srv_rpcparams** возвращает 0.</span><span class="sxs-lookup"><span data-stu-id="24205-164">The SRV_RPC handler is still called, but it appears as if there were no parameters and **srv_rpcparams** returns 0.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="24205-165">Необходимо тщательно просмотреть исходный код расширенных хранимых процедур и проверить скомпилированные библиотеки DLL перед их установкой на рабочий сервер.</span><span class="sxs-lookup"><span data-stu-id="24205-165">You should thoroughly review the source code of extended stored procedures, and you should test the compiled DLLs before you install them on a production server.</span></span> <span data-ttu-id="24205-166">Сведения о проверке безопасности см. на следующем [веб-сайте Майкрософт](https://go.microsoft.com/fwlink/?LinkID=54761&amp;clcid=0x409https://msdn.microsoft.com/security/).</span><span class="sxs-lookup"><span data-stu-id="24205-166">For information about security review and testing, see this [Microsoft Web site](https://go.microsoft.com/fwlink/?LinkID=54761&amp;clcid=0x409https://msdn.microsoft.com/security/).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="24205-167">См. также:</span><span class="sxs-lookup"><span data-stu-id="24205-167">See Also</span></span>  
 <span data-ttu-id="24205-168">[API srv_paraminfo &#40;расширенных хранимых процедур&#41;](srv-paraminfo-extended-stored-procedure-api.md) </span><span class="sxs-lookup"><span data-stu-id="24205-168">[srv_paraminfo &#40;Extended Stored Procedure API&#41;](srv-paraminfo-extended-stored-procedure-api.md) </span></span>  
 [<span data-ttu-id="24205-169">srv_rpcparams (интерфейс API расширенных хранимых процедур)</span><span class="sxs-lookup"><span data-stu-id="24205-169">srv_rpcparams &#40;Extended Stored Procedure API&#41;</span></span>](srv-rpcparams-extended-stored-procedure-api.md)  
  
  
