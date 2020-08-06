---
title: srv_paramset (интерфейс API расширенных хранимых процедур) | Документы Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: stored-procedures
ms.topic: reference
api_name:
- srv_paramset
api_location:
- opends60.dll
topic_type:
- apiref
dev_langs:
- C++
helpviewer_keywords:
- srv_paramset
ms.assetid: 2a509206-a1b8-4b20-b0a2-ef680cef7bd8
author: rothja
ms.author: jroth
ms.openlocfilehash: 9ebe308e5e0c8fc24382582fb71db2f48c77541e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87655731"
---
# <a name="srv_paramset-extended-stored-procedure-api"></a><span data-ttu-id="f52c4-102">srv_paramset (API-интерфейс расширенных хранимых процедур)</span><span class="sxs-lookup"><span data-stu-id="f52c4-102">srv_paramset (Extended Stored Procedure API)</span></span>
    
> [!IMPORTANT]  
>  [!INCLUDE[ssNoteDepFutureDontUse](../../includes/ssnotedepfuturedontuse-md.md)] <span data-ttu-id="f52c4-103">Используйте вместо этого интеграцию со средой CLR.</span><span class="sxs-lookup"><span data-stu-id="f52c4-103">Use CLR integration instead.</span></span>  
  
 <span data-ttu-id="f52c4-104">Устанавливает значение возвратного параметра вызова удаленной хранимой процедуры.</span><span class="sxs-lookup"><span data-stu-id="f52c4-104">Sets the value of a remote stored procedure call return parameter.</span></span> <span data-ttu-id="f52c4-105">Эта функция заменена функцией **srv_paramsetoutput**.</span><span class="sxs-lookup"><span data-stu-id="f52c4-105">This function has been superseded by the **srv_paramsetoutput** function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f52c4-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="f52c4-106">Syntax</span></span>  
  
```  
  
int srv_paramset (  
SRV_PROC *  
srvproc  
,  
int  
n  
,   
void *  
data  
,  
int  
len   
);  
  
```  
  
## <a name="arguments"></a><span data-ttu-id="f52c4-107">Аргументы</span><span class="sxs-lookup"><span data-stu-id="f52c4-107">Arguments</span></span>  
 <span data-ttu-id="f52c4-108">*srvproc*</span><span class="sxs-lookup"><span data-stu-id="f52c4-108">*srvproc*</span></span>  
 <span data-ttu-id="f52c4-109">Указатель на структуру SRV_PROC, представляющую собой дескриптор соединения с клиентом (в данном случае — дескриптор, который получил вызов удаленной хранимой процедуры).</span><span class="sxs-lookup"><span data-stu-id="f52c4-109">Is a pointer to the SRV_PROC structure that is the handle for a particular client connection (in this case, the handle that received the remote stored procedure call).</span></span> <span data-ttu-id="f52c4-110">Эта структура содержит сведения, которые используются библиотекой API-интерфейса расширенных хранимых процедур для управления связью и передачи данных между приложением и клиентом.</span><span class="sxs-lookup"><span data-stu-id="f52c4-110">The structure contains information the Extended Stored Procedure API library uses to manage communication and data between the application and the client.</span></span>  
  
 <span data-ttu-id="f52c4-111">*n*</span><span class="sxs-lookup"><span data-stu-id="f52c4-111">*n*</span></span>  
 <span data-ttu-id="f52c4-112">Указывает номер параметра, который должен быть задан.</span><span class="sxs-lookup"><span data-stu-id="f52c4-112">Indicates the number of the parameter to set.</span></span> <span data-ttu-id="f52c4-113">Первый параметр имеет значение 1.</span><span class="sxs-lookup"><span data-stu-id="f52c4-113">The first parameter is 1.</span></span>  
  
 <span data-ttu-id="f52c4-114">*data*</span><span class="sxs-lookup"><span data-stu-id="f52c4-114">*data*</span></span>  
 <span data-ttu-id="f52c4-115">Указатель на значение данных, которое должно быть отправлено назад клиенту, как возвратный параметр удаленной хранимой процедуры.</span><span class="sxs-lookup"><span data-stu-id="f52c4-115">Is a pointer to the data value to be sent back to the client as the remote stored procedure return parameter.</span></span>  
  
 <span data-ttu-id="f52c4-116">*len*</span><span class="sxs-lookup"><span data-stu-id="f52c4-116">*len*</span></span>  
 <span data-ttu-id="f52c4-117">Указывает фактическую длину данных, которые должны быть возвращены.</span><span class="sxs-lookup"><span data-stu-id="f52c4-117">Specifies the actual length of the data to be returned.</span></span> <span data-ttu-id="f52c4-118">Если тип данных параметра имеет постоянную длину и не допускает значений NULL (например, *srvbit* или *srvint1*), параметр *len* не учитывается.</span><span class="sxs-lookup"><span data-stu-id="f52c4-118">If the data type of the parameter is of a constant length and does not allow null values (for example, *srvbit* or *srvint1*), *len* is ignored.</span></span>  
  
## <a name="returns"></a><span data-ttu-id="f52c4-119">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="f52c4-119">Returns</span></span>  
 <span data-ttu-id="f52c4-120">SUCCEED, если значение параметра было успешно установлено; в противном случае — FAIL.</span><span class="sxs-lookup"><span data-stu-id="f52c4-120">SUCCEED if the parameter value was successfully set; otherwise, FAIL.</span></span> <span data-ttu-id="f52c4-121">Значение FAIL возвращается, если удаленной хранимой процедуры сейчас не существует, если у нее нет параметра с номером *n*, если параметр не является возвращаемым или если аргумент *len* недопустимый.</span><span class="sxs-lookup"><span data-stu-id="f52c4-121">FAIL is returned when there is no current remote stored procedure, when there is no *n*th remote stored procedure parameter, when the parameter is not a return parameter, and when the *len* argument is not legal.</span></span>  
  
 <span data-ttu-id="f52c4-122">Если *len* имеет значение 0, то возвращается NULL.</span><span class="sxs-lookup"><span data-stu-id="f52c4-122">If *len*is 0, it returns NULL.</span></span> <span data-ttu-id="f52c4-123">Единственным способом возвратить значение NULL клиенту является задание параметру *len* значения 0.</span><span class="sxs-lookup"><span data-stu-id="f52c4-123">Setting *len* to 0 is the only way to return NULL to the client.</span></span>  
  
 <span data-ttu-id="f52c4-124">Эта функция возвращает следующие значения, если параметр относится к одному из [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] типов данных.</span><span class="sxs-lookup"><span data-stu-id="f52c4-124">This function returns the following values, if the parameter is one of [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] data types.</span></span>  
  
|<span data-ttu-id="f52c4-125">Новые типы данных</span><span class="sxs-lookup"><span data-stu-id="f52c4-125">New data types</span></span>|<span data-ttu-id="f52c4-126">Длина возвращаемых данных</span><span class="sxs-lookup"><span data-stu-id="f52c4-126">Return data length</span></span>|  
|--------------------|------------------------|  
|`BITN`|<span data-ttu-id="f52c4-127">**NULL:** *len* = 0, data = IG, RET = 0</span><span class="sxs-lookup"><span data-stu-id="f52c4-127">**NULL:** *len* = 0, data = IG, RET = 0</span></span><br /><br /> <span data-ttu-id="f52c4-128">**ZERO:** недоступно</span><span class="sxs-lookup"><span data-stu-id="f52c4-128">**ZERO:** N/A</span></span><br /><br /> <span data-ttu-id="f52c4-129">**>= 255:** Н/Д</span><span class="sxs-lookup"><span data-stu-id="f52c4-129">**>=255:** N/A</span></span><br /><br /> <span data-ttu-id="f52c4-130">**<255:** Н/Д</span><span class="sxs-lookup"><span data-stu-id="f52c4-130">**<255:** N/A</span></span>|  
|`BIGVARCHAR`|<span data-ttu-id="f52c4-131">**NULL:** *len* = 0, data = IG, RET = 1</span><span class="sxs-lookup"><span data-stu-id="f52c4-131">**NULL:** *len* = 0, data = IG, RET = 1</span></span><br /><br /> <span data-ttu-id="f52c4-132">**ZERO:** *len* = IG, data = IG, RET = 0</span><span class="sxs-lookup"><span data-stu-id="f52c4-132">**ZERO:** *len* = IG, data = IG, RET = 0</span></span><br /><br /> <span data-ttu-id="f52c4-133">**>=255:** *len* = max8k, data = valid, RET = 0</span><span class="sxs-lookup"><span data-stu-id="f52c4-133">**>=255:** *len* = max8k, data = valid, RET = 0</span></span><br /><br /> <span data-ttu-id="f52c4-134">**<255:** *len* = <8k, data = valid, RET = 1</span><span class="sxs-lookup"><span data-stu-id="f52c4-134">**<255:** *len* = <8k, data = valid, RET = 1</span></span>|  
|`BIGCHAR`|<span data-ttu-id="f52c4-135">**NULL:** *len* = 0, data = IG, RET = 1</span><span class="sxs-lookup"><span data-stu-id="f52c4-135">**NULL:** *len* = 0, data = IG, RET = 1</span></span><br /><br /> <span data-ttu-id="f52c4-136">**ZERO:** *len* = IG, data = IG, RET = 0</span><span class="sxs-lookup"><span data-stu-id="f52c4-136">**ZERO:** *len* = IG, data = IG, RET = 0</span></span><br /><br /> <span data-ttu-id="f52c4-137">**>=255:** *len* = max8k, data = valid, RET = 0</span><span class="sxs-lookup"><span data-stu-id="f52c4-137">**>=255:** *len* = max8k, data = valid, RET = 0</span></span><br /><br /> <span data-ttu-id="f52c4-138">**<255:** *len* = <8k, data = valid, RET = 1</span><span class="sxs-lookup"><span data-stu-id="f52c4-138">**<255:** *len* = <8k, data = valid, RET = 1</span></span>|  
|`BIGBINARY`|<span data-ttu-id="f52c4-139">**NULL:** *len* = 0, data = IG, RET = 1</span><span class="sxs-lookup"><span data-stu-id="f52c4-139">**NULL:** *len* = 0, data = IG, RET = 1</span></span><br /><br /> <span data-ttu-id="f52c4-140">**ZERO:** *len* = IG, data = IG, RET = 0</span><span class="sxs-lookup"><span data-stu-id="f52c4-140">**ZERO:** *len* = IG, data = IG, RET = 0</span></span><br /><br /> <span data-ttu-id="f52c4-141">**>=255:** *len* = max8k, data = valid, RET = 0</span><span class="sxs-lookup"><span data-stu-id="f52c4-141">**>=255:** *len* = max8k, data = valid, RET = 0</span></span><br /><br /> <span data-ttu-id="f52c4-142">**<255:** *len* = <8k, data = valid, RET = 1</span><span class="sxs-lookup"><span data-stu-id="f52c4-142">**<255:** *len* = <8k, data = valid, RET = 1</span></span>|  
|`BIGVARBINARY`|<span data-ttu-id="f52c4-143">**NULL:** *len* = 0, data = IG, RET = 1</span><span class="sxs-lookup"><span data-stu-id="f52c4-143">**NULL:** *len* = 0, data = IG, RET = 1</span></span><br /><br /> <span data-ttu-id="f52c4-144">**ZERO:** *len* = IG, data = IG, RET = 0</span><span class="sxs-lookup"><span data-stu-id="f52c4-144">**ZERO:** *len* = IG, data = IG, RET = 0</span></span><br /><br /> <span data-ttu-id="f52c4-145">**>=255:** *len* = max8k, data = valid, RET = 0</span><span class="sxs-lookup"><span data-stu-id="f52c4-145">**>=255:** *len* = max8k, data = valid, RET = 0</span></span><br /><br /> <span data-ttu-id="f52c4-146">**<255:** *len* = <8k, data = valid, RET = 1</span><span class="sxs-lookup"><span data-stu-id="f52c4-146">**<255:** *len* = <8k, data = valid, RET = 1</span></span>|  
|<span data-ttu-id="f52c4-147">NCHAR</span><span class="sxs-lookup"><span data-stu-id="f52c4-147">NCHAR</span></span>|<span data-ttu-id="f52c4-148">**NULL:** *len* = 0, data = IG, RET = 1</span><span class="sxs-lookup"><span data-stu-id="f52c4-148">**NULL:** *len* = 0, data = IG, RET = 1</span></span><br /><br /> <span data-ttu-id="f52c4-149">**ZERO:** *len* = IG, data = IG, RET = 0</span><span class="sxs-lookup"><span data-stu-id="f52c4-149">**ZERO:** *len* = IG, data = IG, RET = 0</span></span><br /><br /> <span data-ttu-id="f52c4-150">**>=255:** *len* = max8k, data = valid, RET = 0</span><span class="sxs-lookup"><span data-stu-id="f52c4-150">**>=255:** *len* = max8k, data = valid, RET = 0</span></span><br /><br /> <span data-ttu-id="f52c4-151">**<255:** *len* = <8k, data = valid, RET = 1</span><span class="sxs-lookup"><span data-stu-id="f52c4-151">**<255:** *len* = <8k, data = valid, RET = 1</span></span>|  
|<span data-ttu-id="f52c4-152">NVARCHAR</span><span class="sxs-lookup"><span data-stu-id="f52c4-152">NVARCHAR</span></span>|<span data-ttu-id="f52c4-153">**NULL:** *len* = 0, data = IG, RET = 1</span><span class="sxs-lookup"><span data-stu-id="f52c4-153">**NULL:** *len* = 0, data = IG, RET = 1</span></span><br /><br /> <span data-ttu-id="f52c4-154">**ZERO:** *len* = IG, data = IG, RET = 0</span><span class="sxs-lookup"><span data-stu-id="f52c4-154">**ZERO:** *len* = IG, data = IG, RET = 0</span></span><br /><br /> <span data-ttu-id="f52c4-155">**>=255:** *len* = max8k, data = valid, RET = 0</span><span class="sxs-lookup"><span data-stu-id="f52c4-155">**>=255:** *len* = max8k, data = valid, RET = 0</span></span><br /><br /> <span data-ttu-id="f52c4-156">**<255:** *len* = <8k, data = valid, RET = 1</span><span class="sxs-lookup"><span data-stu-id="f52c4-156">**<255:** *len* = <8k, data = valid, RET = 1</span></span>|  
|`NTEXT`|<span data-ttu-id="f52c4-157">**NULL:** *len* = IG, data = IG, RET = 0</span><span class="sxs-lookup"><span data-stu-id="f52c4-157">**NULL:** *len* = IG, data = IG, RET = 0</span></span><br /><br /> <span data-ttu-id="f52c4-158">**ZERO:** *len* = IG, data = IG, RET = 0</span><span class="sxs-lookup"><span data-stu-id="f52c4-158">**ZERO:** *len* = IG, data = IG, RET = 0</span></span><br /><br /> <span data-ttu-id="f52c4-159">**>=255:** *len* = IG, data = IG, RET = 0</span><span class="sxs-lookup"><span data-stu-id="f52c4-159">**>=255:** *len* = IG, data = IG, RET = 0</span></span><br /><br /> <span data-ttu-id="f52c4-160">\*\* \< 255:\*\* *Len* = и, Data = и, ret = 0</span><span class="sxs-lookup"><span data-stu-id="f52c4-160">**\<255:** *len* = IG, data = IG, RET = 0</span></span>|  
|<span data-ttu-id="f52c4-161">RET = значение, возвращаемое srv_paramset</span><span class="sxs-lookup"><span data-stu-id="f52c4-161">RET = Return value of srv_paramset</span></span>||  
|<span data-ttu-id="f52c4-162">IG = значение будет пропущено</span><span class="sxs-lookup"><span data-stu-id="f52c4-162">IG = Value will be ignored</span></span>||  
|<span data-ttu-id="f52c4-163">valid = любой допустимый указатель на данные</span><span class="sxs-lookup"><span data-stu-id="f52c4-163">valid = Any valid pointer to data</span></span>||  
  
## <a name="remarks"></a><span data-ttu-id="f52c4-164">Remarks</span><span class="sxs-lookup"><span data-stu-id="f52c4-164">Remarks</span></span>  
 <span data-ttu-id="f52c4-165">Параметры содержат данные, передаваемые между клиентами и приложением с удаленной хранимой процедурой.</span><span class="sxs-lookup"><span data-stu-id="f52c4-165">Parameters contain data passed between clients and the application with remote stored procedures.</span></span> <span data-ttu-id="f52c4-166">Клиент может указать некоторые параметры в качестве возвращаемых.</span><span class="sxs-lookup"><span data-stu-id="f52c4-166">The client can specify certain parameters as return parameters.</span></span> <span data-ttu-id="f52c4-167">Эти возвращаемые параметры могут содержать значения, которые серверное приложение служб Open Data Services данных передает клиенту.</span><span class="sxs-lookup"><span data-stu-id="f52c4-167">These return parameters can contain values that the Open Data Services server application passes back to the client.</span></span> <span data-ttu-id="f52c4-168">Использование возвращаемых параметров аналогично передаче параметров по ссылке.</span><span class="sxs-lookup"><span data-stu-id="f52c4-168">Using return parameters is analogous to passing parameters by reference.</span></span>  
  
 <span data-ttu-id="f52c4-169">Возвращаемое значение невозможно задать параметру, который не был запущен как возвращаемый параметр.</span><span class="sxs-lookup"><span data-stu-id="f52c4-169">You cannot set the return value for a parameter that wasn't invoked as a return parameter.</span></span> <span data-ttu-id="f52c4-170">Определить, как был вызван параметр, можно с помощью функции **srv_paramstatus**.</span><span class="sxs-lookup"><span data-stu-id="f52c4-170">You can use **srv_paramstatus** to determine how the parameter was invoked.</span></span>  
  
 <span data-ttu-id="f52c4-171">Эта функция задает параметру возвращаемое значение, но она не отправляет это значение клиенту.</span><span class="sxs-lookup"><span data-stu-id="f52c4-171">This function sets the return value for a parameter but it does not actually send the return value to the client.</span></span> <span data-ttu-id="f52c4-172">Все возвращаемые параметры, независимо от того, были ли их возвращаемые значения заданы с помощью функции **srv_paramset** или нет, автоматически отправляются клиенту при вызове функции **srv_senddone** с установленным флагом состояния SRV_DONE_FINAL.</span><span class="sxs-lookup"><span data-stu-id="f52c4-172">All return parameters, whether their return values have been set with **srv_paramset** or not, are automatically sent to the client when **srv_senddone** is called with the status flag SRV_DONE_FINAL set.</span></span>  
  
 <span data-ttu-id="f52c4-173">Когда удаленная хранимая процедура вызывается с параметрами, эти параметры могут быть переданы либо по имени, либо по позиции — без указания имени.</span><span class="sxs-lookup"><span data-stu-id="f52c4-173">When a remote stored procedure call is made with parameters, the parameters can be passed either by name or by position (unnamed).</span></span> <span data-ttu-id="f52c4-174">Если при вызове удаленной хранимой процедуры часть параметров передается по имени, а часть — по позиции, возникает ошибка.</span><span class="sxs-lookup"><span data-stu-id="f52c4-174">If the remote stored procedure call is made with some parameters passed by name and some passed by position, an error occurs.</span></span> <span data-ttu-id="f52c4-175">Обработчик SRV_RPC по-прежнему вызывается, однако он отображается так, как если бы не имел параметров, а функция **srv_rpcparams** возвращает 0.</span><span class="sxs-lookup"><span data-stu-id="f52c4-175">The SRV_RPC handler is still called, but it appears as if there were no parameters, and **srv_rpcparams** returns 0.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="f52c4-176">Необходимо тщательно просмотреть исходный код расширенных хранимых процедур и проверить скомпилированные библиотеки DLL перед их установкой на рабочий сервер.</span><span class="sxs-lookup"><span data-stu-id="f52c4-176">You should thoroughly review the source code of extended stored procedures, and you should test the compiled DLLs before you install them on a production server.</span></span> <span data-ttu-id="f52c4-177">Сведения о проверке безопасности см. на следующем [веб-сайте Майкрософт](https://go.microsoft.com/fwlink/?LinkID=54761&amp;clcid=0x409https://msdn.microsoft.com/security/).</span><span class="sxs-lookup"><span data-stu-id="f52c4-177">For information about security review and testing, see this [Microsoft Web site](https://go.microsoft.com/fwlink/?LinkID=54761&amp;clcid=0x409https://msdn.microsoft.com/security/).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f52c4-178">См. также:</span><span class="sxs-lookup"><span data-stu-id="f52c4-178">See Also</span></span>  
 [<span data-ttu-id="f52c4-179">srv_paramsetoutput (интерфейс API расширенных хранимых процедур)</span><span class="sxs-lookup"><span data-stu-id="f52c4-179">srv_paramsetoutput &#40;Extended Stored Procedure API&#41;</span></span>](srv-paramsetoutput-extended-stored-procedure-api.md)  
  
  
