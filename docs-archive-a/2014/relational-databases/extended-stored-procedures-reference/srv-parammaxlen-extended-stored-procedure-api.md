---
title: srv_parammaxlen (интерфейс API расширенных хранимых процедур) | Документы Майкрософт
ms.custom: ''
ms.date: 03/08/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: stored-procedures
ms.topic: reference
api_name:
- srv_parammaxlen
api_location:
- opends60.dll
topic_type:
- apiref
dev_langs:
- C++
helpviewer_keywords:
- srv_parammaxlen
ms.assetid: 49bfc29d-f76a-4963-b0e6-b8532dfda850
author: rothja
ms.author: jroth
ms.openlocfilehash: b289743b3de4b115a67a029dcc0261854ee3a40b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87751024"
---
# <a name="srv_parammaxlen-extended-stored-procedure-api"></a><span data-ttu-id="93d27-102">srv_parammaxlen (API-интерфейс расширенных хранимых процедур)</span><span class="sxs-lookup"><span data-stu-id="93d27-102">srv_parammaxlen (Extended Stored Procedure API)</span></span>
    
> [!IMPORTANT]  
>  [!INCLUDE[ssNoteDepFutureDontUse](../../includes/ssnotedepfuturedontuse-md.md)] <span data-ttu-id="93d27-103">Используйте вместо этого интеграцию со средой CLR.</span><span class="sxs-lookup"><span data-stu-id="93d27-103">Use CLR integration instead.</span></span>  
  
 <span data-ttu-id="93d27-104">Возвращает наибольший размер данных параметра вызова удаленной хранимой процедуры.</span><span class="sxs-lookup"><span data-stu-id="93d27-104">Returns the maximum data length of a remote stored procedure call parameter.</span></span> <span data-ttu-id="93d27-105">Эта функция заменена функцией **srv_paraminfo**.</span><span class="sxs-lookup"><span data-stu-id="93d27-105">This function has been superseded by the **srv_paraminfo** function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="93d27-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="93d27-106">Syntax</span></span>  
  
```  
  
int srv_parammaxlen (  
SRV_PROC *  
srvproc  
,  
int  
n   
);  
  
```  
  
## <a name="arguments"></a><span data-ttu-id="93d27-107">Аргументы</span><span class="sxs-lookup"><span data-stu-id="93d27-107">Arguments</span></span>  
 <span data-ttu-id="93d27-108">*srvproc*</span><span class="sxs-lookup"><span data-stu-id="93d27-108">*srvproc*</span></span>  
 <span data-ttu-id="93d27-109">Указатель на структуру SRV_PROC, представляющую собой дескриптор соединения с клиентом (в данном случае — дескриптор, который получил вызов удаленной хранимой процедуры).</span><span class="sxs-lookup"><span data-stu-id="93d27-109">Is a pointer to the SRV_PROC structure that is the handle for a particular client connection (in this case, the handle that received the remote stored procedure call).</span></span> <span data-ttu-id="93d27-110">Эта структура содержит сведения, которые используются библиотекой API-интерфейса расширенных хранимых процедур для управления связью и передачи данных между приложением и клиентом.</span><span class="sxs-lookup"><span data-stu-id="93d27-110">The structure contains information the Extended Stored Procedure API library uses to manage communication and data between the application and the client.</span></span>  
  
 <span data-ttu-id="93d27-111">*n*</span><span class="sxs-lookup"><span data-stu-id="93d27-111">*n*</span></span>  
 <span data-ttu-id="93d27-112">Указывает номер параметра.</span><span class="sxs-lookup"><span data-stu-id="93d27-112">Indicates the number of the parameter.</span></span> <span data-ttu-id="93d27-113">Первый параметр имеет значение 1.</span><span class="sxs-lookup"><span data-stu-id="93d27-113">The first parameter is 1.</span></span>  
  
## <a name="returns"></a><span data-ttu-id="93d27-114">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="93d27-114">Returns</span></span>  
 <span data-ttu-id="93d27-115">Наибольшая длина данных параметра в байтах.</span><span class="sxs-lookup"><span data-stu-id="93d27-115">The maximum length, in bytes, of the parameter data.</span></span> <span data-ttu-id="93d27-116">Если отсутствует *n*-й параметр или удаленная хранимая процедура, то возвращается значение -1.</span><span class="sxs-lookup"><span data-stu-id="93d27-116">If there is no *n*th parameter or if there is no remote stored procedure, it returns -1.</span></span>  
  
 <span data-ttu-id="93d27-117">Эта функция возвращает следующие значения, если параметр имеет один из следующих [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] типов данных.</span><span class="sxs-lookup"><span data-stu-id="93d27-117">This function returns the following values, if the parameter is one of the following [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] data types.</span></span>  
  
|<span data-ttu-id="93d27-118">Новые типы данных</span><span class="sxs-lookup"><span data-stu-id="93d27-118">New data types</span></span>|<span data-ttu-id="93d27-119">Длина входных данных</span><span class="sxs-lookup"><span data-stu-id="93d27-119">Input data length</span></span>|  
|--------------------|-----------------------|  
|`BITN`|<span data-ttu-id="93d27-120">**NULL:** 1</span><span class="sxs-lookup"><span data-stu-id="93d27-120">**NULL:** 1</span></span><br /><br /> <span data-ttu-id="93d27-121">**Ноль:** 1</span><span class="sxs-lookup"><span data-stu-id="93d27-121">**ZERO:** 1</span></span><br /><br /> <span data-ttu-id="93d27-122">**>= 255:** Н/Д</span><span class="sxs-lookup"><span data-stu-id="93d27-122">**>=255:** N/A</span></span><br /><br /> <span data-ttu-id="93d27-123">**<255:** Н/Д</span><span class="sxs-lookup"><span data-stu-id="93d27-123">**<255:** N/A</span></span>|  
|`BIGVARCHAR`|<span data-ttu-id="93d27-124">**NULL:** 255</span><span class="sxs-lookup"><span data-stu-id="93d27-124">**NULL:** 255</span></span><br /><br /> <span data-ttu-id="93d27-125">**ZERO:** 255</span><span class="sxs-lookup"><span data-stu-id="93d27-125">**ZERO:** 255</span></span><br /><br /> <span data-ttu-id="93d27-126">**>= 255:** 255</span><span class="sxs-lookup"><span data-stu-id="93d27-126">**>=255:** 255</span></span><br /><br /> <span data-ttu-id="93d27-127">**<255:** 255</span><span class="sxs-lookup"><span data-stu-id="93d27-127">**<255:** 255</span></span>|  
|`BIGCHAR`|<span data-ttu-id="93d27-128">**NULL:** 255</span><span class="sxs-lookup"><span data-stu-id="93d27-128">**NULL:** 255</span></span><br /><br /> <span data-ttu-id="93d27-129">**ZERO:** 255</span><span class="sxs-lookup"><span data-stu-id="93d27-129">**ZERO:** 255</span></span><br /><br /> <span data-ttu-id="93d27-130">**>= 255:** 255</span><span class="sxs-lookup"><span data-stu-id="93d27-130">**>=255:** 255</span></span><br /><br /> <span data-ttu-id="93d27-131">**<255:** 255</span><span class="sxs-lookup"><span data-stu-id="93d27-131">**<255:** 255</span></span>|  
|`BIGBINARY`|<span data-ttu-id="93d27-132">**NULL:** 255</span><span class="sxs-lookup"><span data-stu-id="93d27-132">**NULL:** 255</span></span><br /><br /> <span data-ttu-id="93d27-133">**ZERO:** 255</span><span class="sxs-lookup"><span data-stu-id="93d27-133">**ZERO:** 255</span></span><br /><br /> <span data-ttu-id="93d27-134">**>= 255:** 255</span><span class="sxs-lookup"><span data-stu-id="93d27-134">**>=255:** 255</span></span><br /><br /> <span data-ttu-id="93d27-135">**<255:** 255</span><span class="sxs-lookup"><span data-stu-id="93d27-135">**<255:** 255</span></span>|  
|`BIGVARBINARY`|<span data-ttu-id="93d27-136">**NULL:** 255</span><span class="sxs-lookup"><span data-stu-id="93d27-136">**NULL:** 255</span></span><br /><br /> <span data-ttu-id="93d27-137">**ZERO:** 255</span><span class="sxs-lookup"><span data-stu-id="93d27-137">**ZERO:** 255</span></span><br /><br /> <span data-ttu-id="93d27-138">**>= 255:** 255</span><span class="sxs-lookup"><span data-stu-id="93d27-138">**>=255:** 255</span></span><br /><br /> <span data-ttu-id="93d27-139">**<255:** 255</span><span class="sxs-lookup"><span data-stu-id="93d27-139">**<255:** 255</span></span>|  
|`NCHAR`|<span data-ttu-id="93d27-140">**NULL:** 255</span><span class="sxs-lookup"><span data-stu-id="93d27-140">**NULL:** 255</span></span><br /><br /> <span data-ttu-id="93d27-141">**ZERO:** 255</span><span class="sxs-lookup"><span data-stu-id="93d27-141">**ZERO:** 255</span></span><br /><br /> <span data-ttu-id="93d27-142">**>= 255:** 255</span><span class="sxs-lookup"><span data-stu-id="93d27-142">**>=255:** 255</span></span><br /><br /> <span data-ttu-id="93d27-143">**<255:** 255</span><span class="sxs-lookup"><span data-stu-id="93d27-143">**<255:** 255</span></span>|  
|`NVARCHAR`|<span data-ttu-id="93d27-144">**NULL:** 255</span><span class="sxs-lookup"><span data-stu-id="93d27-144">**NULL:** 255</span></span><br /><br /> <span data-ttu-id="93d27-145">**ZERO:** 255</span><span class="sxs-lookup"><span data-stu-id="93d27-145">**ZERO:** 255</span></span><br /><br /> <span data-ttu-id="93d27-146">**>= 255:** 255</span><span class="sxs-lookup"><span data-stu-id="93d27-146">**>=255:** 255</span></span><br /><br /> <span data-ttu-id="93d27-147">**<255:** 255</span><span class="sxs-lookup"><span data-stu-id="93d27-147">**<255:** 255</span></span>|  
|`NTEXT`|<span data-ttu-id="93d27-148">**Null:** -1</span><span class="sxs-lookup"><span data-stu-id="93d27-148">**NULL:** -1</span></span><br /><br /> <span data-ttu-id="93d27-149">**ZERO:** –1</span><span class="sxs-lookup"><span data-stu-id="93d27-149">**ZERO:** -1</span></span><br /><br /> <span data-ttu-id="93d27-150">**>= 255:** -1</span><span class="sxs-lookup"><span data-stu-id="93d27-150">**>=255:** -1</span></span><br /><br /> <span data-ttu-id="93d27-151">\*\* \< 255:\*\* -1</span><span class="sxs-lookup"><span data-stu-id="93d27-151">**\<255:** -1</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="93d27-152">Remarks</span><span class="sxs-lookup"><span data-stu-id="93d27-152">Remarks</span></span>  
 <span data-ttu-id="93d27-153">У каждого параметра удаленной хранимой процедуры есть максимальная и реальная длина данных.</span><span class="sxs-lookup"><span data-stu-id="93d27-153">Each remote stored procedure parameter has an actual and a maximum data length.</span></span> <span data-ttu-id="93d27-154">Для стандартных типов данных с фиксированной длиной, которые не поддерживают значений NULL, реальная и максимальная длина одинаковы.</span><span class="sxs-lookup"><span data-stu-id="93d27-154">For standard fixed-length data types that do not allow null values, the actual and maximum lengths are the same.</span></span> <span data-ttu-id="93d27-155">У типов данных переменной длины эти длины могут быть разными.</span><span class="sxs-lookup"><span data-stu-id="93d27-155">For variable-length data types, the lengths can vary.</span></span> <span data-ttu-id="93d27-156">Например, параметр, объявленный как **varchar(30)**, может иметь данные длиной всего 10 байт.</span><span class="sxs-lookup"><span data-stu-id="93d27-156">For example, a parameter declared as **varchar(30)** can have data that is only 10 bytes long.</span></span> <span data-ttu-id="93d27-157">Фактическая длина параметра — 10, а максимальная — 30.</span><span class="sxs-lookup"><span data-stu-id="93d27-157">The parameter's actual length is 10 and its maximum length is 30.</span></span> <span data-ttu-id="93d27-158">Функция **srv_parammaxlen** возвращает максимальную длину данных удаленной хранимой процедуры.</span><span class="sxs-lookup"><span data-stu-id="93d27-158">The **srv_parammaxlen** function gets the maximum data length of a remote stored procedure.</span></span> <span data-ttu-id="93d27-159">Чтобы получить фактическую длину параметра, используйте функцию **srv_paramlen**.</span><span class="sxs-lookup"><span data-stu-id="93d27-159">To obtain the actual length of a parameter, use **srv_paramlen**.</span></span>  
  
 <span data-ttu-id="93d27-160">Когда удаленная хранимая процедура вызывается с параметрами, эти параметры могут быть переданы либо по имени, либо по позиции — без указания имени.</span><span class="sxs-lookup"><span data-stu-id="93d27-160">When a remote stored procedure call is made with parameters, the parameters can be passed either by name or by position (unnamed).</span></span> <span data-ttu-id="93d27-161">Если при вызове удаленной хранимой процедуры часть параметров передается по имени, а часть — по позиции, возникает ошибка.</span><span class="sxs-lookup"><span data-stu-id="93d27-161">If the remote stored procedure call is made with some parameters passed by name and some passed by position, an error occurs.</span></span> <span data-ttu-id="93d27-162">Обработчик SRV_RPC по-прежнему вызывается, однако он отображается так, как если бы не имел параметров, а функция **srv_rpcparams** возвращает 0.</span><span class="sxs-lookup"><span data-stu-id="93d27-162">The SRV_RPC handler is still called, but it appears as if there were no parameters, and **srv_rpcparams** returns 0.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="93d27-163">Необходимо тщательно просмотреть исходный код расширенных хранимых процедур и проверить скомпилированные библиотеки DLL перед их установкой на рабочий сервер.</span><span class="sxs-lookup"><span data-stu-id="93d27-163">You should thoroughly review the source code of extended stored procedures, and you should test the compiled DLLs before you install them on a production server.</span></span> <span data-ttu-id="93d27-164">Сведения о проверке безопасности см. на следующем [веб-сайте Майкрософт](https://go.microsoft.com/fwlink/?LinkID=54761&amp;clcid=0x409https://msdn.microsoft.com/security/).</span><span class="sxs-lookup"><span data-stu-id="93d27-164">For information about security review and testing, see this [Microsoft Web site](https://go.microsoft.com/fwlink/?LinkID=54761&amp;clcid=0x409https://msdn.microsoft.com/security/).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="93d27-165">См. также:</span><span class="sxs-lookup"><span data-stu-id="93d27-165">See Also</span></span>  
 <span data-ttu-id="93d27-166">[API srv_paraminfo &#40;расширенных хранимых процедур&#41;](srv-paraminfo-extended-stored-procedure-api.md) </span><span class="sxs-lookup"><span data-stu-id="93d27-166">[srv_paraminfo &#40;Extended Stored Procedure API&#41;](srv-paraminfo-extended-stored-procedure-api.md) </span></span>  
 [<span data-ttu-id="93d27-167">srv_rpcparams (интерфейс API расширенных хранимых процедур)</span><span class="sxs-lookup"><span data-stu-id="93d27-167">srv_rpcparams &#40;Extended Stored Procedure API&#41;</span></span>](srv-rpcparams-extended-stored-procedure-api.md)  
  
  
