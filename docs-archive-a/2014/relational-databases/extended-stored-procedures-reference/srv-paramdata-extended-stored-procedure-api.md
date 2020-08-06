---
title: srv_paramdata (интерфейс API расширенных хранимых процедур) | Документы Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: stored-procedures
ms.topic: reference
api_name:
- srv_paramdata
api_location:
- opends60.dll
topic_type:
- apiref
dev_langs:
- C++
helpviewer_keywords:
- srv_paramdata
ms.assetid: 3104514d-b404-47c9-b6d7-928106384874
author: rothja
ms.author: jroth
ms.openlocfilehash: 092ca5b811a12c3e6b199a6041ce6e4f8e02f4b7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87666610"
---
# <a name="srv_paramdata-extended-stored-procedure-api"></a><span data-ttu-id="e88de-102">srv_paramdata (API-интерфейс расширенных хранимых процедур)</span><span class="sxs-lookup"><span data-stu-id="e88de-102">srv_paramdata (Extended Stored Procedure API)</span></span>
    
> [!IMPORTANT]  
>  [!INCLUDE[ssNoteDepFutureDontUse](../../includes/ssnotedepfuturedontuse-md.md)] <span data-ttu-id="e88de-103">Используйте вместо этого интеграцию со средой CLR.</span><span class="sxs-lookup"><span data-stu-id="e88de-103">Use CLR integration instead.</span></span>  
  
 <span data-ttu-id="e88de-104">Возвращает значение параметра вызова удаленной хранимой процедуры.</span><span class="sxs-lookup"><span data-stu-id="e88de-104">Returns the value of a remote stored procedure call parameter.</span></span> <span data-ttu-id="e88de-105">Эта функция заменена функцией **srv_paraminfo**.</span><span class="sxs-lookup"><span data-stu-id="e88de-105">This function has been superseded by the **srv_paraminfo** function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e88de-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="e88de-106">Syntax</span></span>  
  
```  
  
void * srv_paramdata (  
SRV_PROC *  
srvproc  
,  
int  
n   
);  
  
```  
  
## <a name="arguments"></a><span data-ttu-id="e88de-107">Аргументы</span><span class="sxs-lookup"><span data-stu-id="e88de-107">Arguments</span></span>  
 <span data-ttu-id="e88de-108">*srvproc*</span><span class="sxs-lookup"><span data-stu-id="e88de-108">*srvproc*</span></span>  
 <span data-ttu-id="e88de-109">Указатель на структуру SRV_PROC, представляющую собой дескриптор соединения с клиентом (в данном случае — дескриптор, который получил вызов удаленной хранимой процедуры).</span><span class="sxs-lookup"><span data-stu-id="e88de-109">Is a pointer to the SRV_PROC structure that is the handle for a particular client connection (in this case, the handle that received the remote stored procedure call).</span></span> <span data-ttu-id="e88de-110">Эта структура содержит сведения, которые используются библиотекой расширенных хранимых процедур для управления связью и передачи данных между приложением и клиентом.</span><span class="sxs-lookup"><span data-stu-id="e88de-110">The structure contains information the Extended Stored Procedure library uses to manage communication and data between the application and the client.</span></span>  
  
 <span data-ttu-id="e88de-111">*n*</span><span class="sxs-lookup"><span data-stu-id="e88de-111">*n*</span></span>  
 <span data-ttu-id="e88de-112">Номер параметра.</span><span class="sxs-lookup"><span data-stu-id="e88de-112">Is the number of the parameter.</span></span> <span data-ttu-id="e88de-113">Первый параметр имеет номер 1.</span><span class="sxs-lookup"><span data-stu-id="e88de-113">The first parameter is number 1.</span></span>  
  
## <a name="returns"></a><span data-ttu-id="e88de-114">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="e88de-114">Returns</span></span>  
 <span data-ttu-id="e88de-115">Указатель на значение параметра.</span><span class="sxs-lookup"><span data-stu-id="e88de-115">A pointer to the parameter value.</span></span> <span data-ttu-id="e88de-116">Если параметр с номером *n* имеет значение NULL, или если параметра с номером *n* или удаленной хранимой процедуры не существует, то возвращается значение NULL.</span><span class="sxs-lookup"><span data-stu-id="e88de-116">If the *n*th parameter is NULL, there is no *n*th parameter, or there is no remote stored procedure, returns NULL.</span></span> <span data-ttu-id="e88de-117">Если значением параметра является строка, она не может завершаться нулевым байтом.</span><span class="sxs-lookup"><span data-stu-id="e88de-117">If the parameter value is a string, it might not be null-terminated.</span></span> <span data-ttu-id="e88de-118">Используйте функцию **srv_paramlen**, чтобы определить длину строки.</span><span class="sxs-lookup"><span data-stu-id="e88de-118">Use **srv_paramlen** to determine the length of the string.</span></span>  
  
 <span data-ttu-id="e88de-119">Эта функция возвращает следующие значения, если параметр относится к одному из [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] типов данных.</span><span class="sxs-lookup"><span data-stu-id="e88de-119">This function returns the following values, if the parameter is one of the [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] data types.</span></span> <span data-ttu-id="e88de-120">В данных указателя показано, является ли этот указатель допустимым для типа данных (VP), NULL или не применимым (N/A), а также содержимое тех данных, на которые он указывает.</span><span class="sxs-lookup"><span data-stu-id="e88de-120">Pointer data includes whether the pointer for the data type is valid (VP), NULL, or not applicable (N/A), and the contents of the data pointed to.</span></span>  
  
|<span data-ttu-id="e88de-121">Новые типы данных</span><span class="sxs-lookup"><span data-stu-id="e88de-121">New data types</span></span>|<span data-ttu-id="e88de-122">Длина входных данных</span><span class="sxs-lookup"><span data-stu-id="e88de-122">Input data length</span></span>|  
|--------------------|-----------------------|  
|<span data-ttu-id="e88de-123">BITN</span><span class="sxs-lookup"><span data-stu-id="e88de-123">BITN</span></span>|<span data-ttu-id="e88de-124">**NULL:** VP, NULL</span><span class="sxs-lookup"><span data-stu-id="e88de-124">**NULL:** VP, NULL</span></span><br /><br /> <span data-ttu-id="e88de-125">**ZERO:** VP, NULL</span><span class="sxs-lookup"><span data-stu-id="e88de-125">**ZERO:** VP, NULL</span></span><br /><br /> <span data-ttu-id="e88de-126">**>= 255:** Н/Д</span><span class="sxs-lookup"><span data-stu-id="e88de-126">**>=255:** N/A</span></span><br /><br /> <span data-ttu-id="e88de-127">**<255:** Н/Д</span><span class="sxs-lookup"><span data-stu-id="e88de-127">**<255:** N/A</span></span>|  
|<span data-ttu-id="e88de-128">BIGVARCHAR</span><span class="sxs-lookup"><span data-stu-id="e88de-128">BIGVARCHAR</span></span>|<span data-ttu-id="e88de-129">**NULL:** NULL, недоступно</span><span class="sxs-lookup"><span data-stu-id="e88de-129">**NULL:** NULL, N/A</span></span><br /><br /> <span data-ttu-id="e88de-130">**ZERO:** VP, NULL</span><span class="sxs-lookup"><span data-stu-id="e88de-130">**ZERO:** VP, NULL</span></span><br /><br /> <span data-ttu-id="e88de-131">**>=255:** VP, 255 символов</span><span class="sxs-lookup"><span data-stu-id="e88de-131">**>=255:** VP, 255 chars</span></span><br /><br /> <span data-ttu-id="e88de-132">**<255:** VP, фактические данные</span><span class="sxs-lookup"><span data-stu-id="e88de-132">**<255:** VP, actual data</span></span>|  
|<span data-ttu-id="e88de-133">BIGCHAR</span><span class="sxs-lookup"><span data-stu-id="e88de-133">BIGCHAR</span></span>|<span data-ttu-id="e88de-134">**NULL:** NULL, недоступно</span><span class="sxs-lookup"><span data-stu-id="e88de-134">**NULL:** NULL, N/A</span></span><br /><br /> <span data-ttu-id="e88de-135">**ZERO:** VP, 255 пробелов</span><span class="sxs-lookup"><span data-stu-id="e88de-135">**ZERO:** VP, 255 spaces</span></span><br /><br /> <span data-ttu-id="e88de-136">**>=255:** VP, 255 символов</span><span class="sxs-lookup"><span data-stu-id="e88de-136">**>=255:** VP, 255 chars</span></span><br /><br /> <span data-ttu-id="e88de-137">**<255:** VP, фактические данные + заполнение (до 255)</span><span class="sxs-lookup"><span data-stu-id="e88de-137">**<255:** VP, actual data + padding (up to 255)</span></span>|  
|<span data-ttu-id="e88de-138">BIGBINARY</span><span class="sxs-lookup"><span data-stu-id="e88de-138">BIGBINARY</span></span>|<span data-ttu-id="e88de-139">**NULL:** NULL, недоступно</span><span class="sxs-lookup"><span data-stu-id="e88de-139">**NULL:** NULL, N/A</span></span><br /><br /> <span data-ttu-id="e88de-140">**ZERO:** VP, 255 0x00</span><span class="sxs-lookup"><span data-stu-id="e88de-140">**ZERO:** VP, 255 0x00</span></span><br /><br /> <span data-ttu-id="e88de-141">**>=255:** VP, 255 байт</span><span class="sxs-lookup"><span data-stu-id="e88de-141">**>=255:** VP, 255 bytes</span></span><br /><br /> <span data-ttu-id="e88de-142">**<255:** VP, фактические данные + заполнение (до 255)</span><span class="sxs-lookup"><span data-stu-id="e88de-142">**<255:** VP, actual data + padding (up to 255)</span></span>|  
|<span data-ttu-id="e88de-143">BIGVARBINARY</span><span class="sxs-lookup"><span data-stu-id="e88de-143">BIGVARBINARY</span></span>|<span data-ttu-id="e88de-144">**NULL:** NULL, недоступно</span><span class="sxs-lookup"><span data-stu-id="e88de-144">**NULL:** NULL, N/A</span></span><br /><br /> <span data-ttu-id="e88de-145">**ZERO:** VP, 0x00</span><span class="sxs-lookup"><span data-stu-id="e88de-145">**ZERO:** VP, 0x00</span></span><br /><br /> <span data-ttu-id="e88de-146">**>=255:** VP, 255 байт</span><span class="sxs-lookup"><span data-stu-id="e88de-146">**>=255:** VP, 255 bytes</span></span><br /><br /> <span data-ttu-id="e88de-147">**<255:** VP, фактические данные</span><span class="sxs-lookup"><span data-stu-id="e88de-147">**<255:** VP, actual data</span></span>|  
|<span data-ttu-id="e88de-148">NCHAR</span><span class="sxs-lookup"><span data-stu-id="e88de-148">NCHAR</span></span>|<span data-ttu-id="e88de-149">**NULL:** NULL, недоступно</span><span class="sxs-lookup"><span data-stu-id="e88de-149">**NULL:** NULL, N/A</span></span><br /><br /> <span data-ttu-id="e88de-150">**ZERO:** VP, 255 пробелов</span><span class="sxs-lookup"><span data-stu-id="e88de-150">**ZERO:** VP, 255 spaces</span></span><br /><br /> <span data-ttu-id="e88de-151">**>=255:** VP, 255 символов</span><span class="sxs-lookup"><span data-stu-id="e88de-151">**>=255:** VP, 255 chars</span></span><br /><br /> <span data-ttu-id="e88de-152">**<255:** VP, фактические данные + заполнение (до 255)</span><span class="sxs-lookup"><span data-stu-id="e88de-152">**<255:** VP, actual data + padding (up to 255)</span></span>|  
|<span data-ttu-id="e88de-153">NVARCHAR</span><span class="sxs-lookup"><span data-stu-id="e88de-153">NVARCHAR</span></span>|<span data-ttu-id="e88de-154">**NULL:** NULL, недоступно</span><span class="sxs-lookup"><span data-stu-id="e88de-154">**NULL:** NULL, N/A</span></span><br /><br /> <span data-ttu-id="e88de-155">**ZERO:** VP, NULL</span><span class="sxs-lookup"><span data-stu-id="e88de-155">**ZERO:** VP, NULL</span></span><br /><br /> <span data-ttu-id="e88de-156">**>=255:** VP, 255 символов</span><span class="sxs-lookup"><span data-stu-id="e88de-156">**>=255:** VP, 255 chars</span></span><br /><br /> <span data-ttu-id="e88de-157">**<255:** VP, фактические данные</span><span class="sxs-lookup"><span data-stu-id="e88de-157">**<255:** VP, actual data</span></span>|  
|<span data-ttu-id="e88de-158">NTEXT</span><span class="sxs-lookup"><span data-stu-id="e88de-158">NTEXT</span></span>|<span data-ttu-id="e88de-159">**NULL:** недоступно</span><span class="sxs-lookup"><span data-stu-id="e88de-159">**NULL:** N/A</span></span><br /><br /> <span data-ttu-id="e88de-160">**ZERO:** недоступно</span><span class="sxs-lookup"><span data-stu-id="e88de-160">**ZERO:** N/A</span></span><br /><br /> <span data-ttu-id="e88de-161">**>= 255:** Н/Д</span><span class="sxs-lookup"><span data-stu-id="e88de-161">**>=255:** N/A</span></span><br /><br /> <span data-ttu-id="e88de-162">\*\* \< 255:\*\* н/д</span><span class="sxs-lookup"><span data-stu-id="e88de-162">**\<255:** N/A</span></span>|  
  
 <span data-ttu-id="e88de-163">\* Данные не завершаются нулевым байтом; при отсечении данных >255 символов предупреждение не выдается.</span><span class="sxs-lookup"><span data-stu-id="e88de-163">\*   data is not null-terminated; no warning is issued on truncation for data >255 characters.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e88de-164">Remarks</span><span class="sxs-lookup"><span data-stu-id="e88de-164">Remarks</span></span>  
 <span data-ttu-id="e88de-165">Если известно имя параметра, то с помощью функции **srv_paramnumber** можно возвратить его номер.</span><span class="sxs-lookup"><span data-stu-id="e88de-165">If you know the parameter name, you can use **srv_paramnumber** to get the parameter number.</span></span> <span data-ttu-id="e88de-166">Используйте функцию **srv_paramlen**, чтобы определить, имеет ли параметр значение NULL.</span><span class="sxs-lookup"><span data-stu-id="e88de-166">To determine whether a parameter is NULL, use **srv_paramlen**.</span></span>  
  
 <span data-ttu-id="e88de-167">Когда удаленная хранимая процедура вызывается с параметрами, то эти параметры могут быть переданы либо по имени, либо по позиции (без указания имени).</span><span class="sxs-lookup"><span data-stu-id="e88de-167">When a remote stored procedure call is made with parameters, the parameters can be passed by name or by position (unnamed).</span></span> <span data-ttu-id="e88de-168">Если при вызове удаленной хранимой процедуры часть параметров передается по имени, а часть — по позиции, возникает ошибка.</span><span class="sxs-lookup"><span data-stu-id="e88de-168">If the remote stored procedure call is made with some parameters passed by name and some passed by position, an error occurs.</span></span> <span data-ttu-id="e88de-169">Обработчик SRV_RPC вызывается и при возникновении ошибки, однако он действует так, как будто параметры не были переданы, и функция **srv_rpcparams** возвращает значение 0.</span><span class="sxs-lookup"><span data-stu-id="e88de-169">If an error occurs, the SRV_RPC handler is still called, but it appears as if there were no parameters and **srv_rpcparams** returns 0.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="e88de-170">Необходимо тщательно просмотреть исходный код расширенных хранимых процедур и проверить скомпилированные библиотеки DLL перед их установкой на рабочий сервер.</span><span class="sxs-lookup"><span data-stu-id="e88de-170">You should thoroughly review the source code of extended stored procedures, and you should test the compiled DLLs before you install them on a production server.</span></span> <span data-ttu-id="e88de-171">Сведения о проверке безопасности см. на следующем [веб-сайте Майкрософт](https://go.microsoft.com/fwlink/?LinkID=54761&amp;clcid=0x409https://msdn.microsoft.com/security/).</span><span class="sxs-lookup"><span data-stu-id="e88de-171">For information about security review and testing, see this [Microsoft Web site](https://go.microsoft.com/fwlink/?LinkID=54761&amp;clcid=0x409https://msdn.microsoft.com/security/).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e88de-172">См. также:</span><span class="sxs-lookup"><span data-stu-id="e88de-172">See Also</span></span>  
 [<span data-ttu-id="e88de-173">srv_rpcparams (интерфейс API расширенных хранимых процедур)</span><span class="sxs-lookup"><span data-stu-id="e88de-173">srv_rpcparams &#40;Extended Stored Procedure API&#41;</span></span>](srv-rpcparams-extended-stored-procedure-api.md)  
  
  
