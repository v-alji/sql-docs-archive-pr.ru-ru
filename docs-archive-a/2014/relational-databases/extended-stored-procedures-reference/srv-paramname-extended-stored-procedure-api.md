---
title: srv_paramname (интерфейс API расширенных хранимых процедур) | Документы Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: stored-procedures
ms.topic: reference
api_name:
- srv_paramname
api_location:
- opends60.dll
topic_type:
- apiref
dev_langs:
- C++
helpviewer_keywords:
- srv_paramname
ms.assetid: 1a53d707-7b06-49cc-a0df-ac727cfe953f
author: rothja
ms.author: jroth
ms.openlocfilehash: 2227ac3d46efe7d09abc05964248229f3533d42d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87751023"
---
# <a name="srv_paramname-extended-stored-procedure-api"></a><span data-ttu-id="51355-102">srv_paramname (API-интерфейс расширенных хранимых процедур)</span><span class="sxs-lookup"><span data-stu-id="51355-102">srv_paramname (Extended Stored Procedure API)</span></span>
    
> [!IMPORTANT]  
>  [!INCLUDE[ssNoteDepFutureDontUse](../../includes/ssnotedepfuturedontuse-md.md)] <span data-ttu-id="51355-103">Используйте вместо этого интеграцию со средой CLR.</span><span class="sxs-lookup"><span data-stu-id="51355-103">Use CLR integration instead.</span></span>  
  
 <span data-ttu-id="51355-104">Возвращает имя параметра вызова удаленной хранимой процедуры.</span><span class="sxs-lookup"><span data-stu-id="51355-104">Returns the name of a remote stored procedure call parameter.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="51355-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="51355-105">Syntax</span></span>  
  
```  
  
DBCHAR * srv_paramname (  
SRV_PROC * srvproc,intn, int *len );  
```  
  
## <a name="arguments"></a><span data-ttu-id="51355-106">Аргументы</span><span class="sxs-lookup"><span data-stu-id="51355-106">Arguments</span></span>  
 <span data-ttu-id="51355-107">*srvproc*</span><span class="sxs-lookup"><span data-stu-id="51355-107">*srvproc*</span></span>  
 <span data-ttu-id="51355-108">Указатель на структуру SRV_PROC, представляющую собой дескриптор соединения с клиентом (в данном случае — дескриптор, который получил вызов удаленной хранимой процедуры).</span><span class="sxs-lookup"><span data-stu-id="51355-108">Is a pointer to the SRV_PROC structure that is the handle for a particular client connection (in this case, the handle that received the remote stored procedure call).</span></span> <span data-ttu-id="51355-109">Эта структура содержит сведения, которые используются библиотекой API-интерфейса расширенных хранимых процедур для управления связью и передачи данных между приложением и клиентом.</span><span class="sxs-lookup"><span data-stu-id="51355-109">The structure contains information the Extended Stored Procedure API library uses to manage communication and data between the application and the client.</span></span>  
  
 <span data-ttu-id="51355-110">*n*</span><span class="sxs-lookup"><span data-stu-id="51355-110">*n*</span></span>  
 <span data-ttu-id="51355-111">Указывает номер параметра.</span><span class="sxs-lookup"><span data-stu-id="51355-111">Indicates the number of the parameter.</span></span> <span data-ttu-id="51355-112">Первый параметр имеет значение 1.</span><span class="sxs-lookup"><span data-stu-id="51355-112">The first parameter is 1.</span></span>  
  
 <span data-ttu-id="51355-113">*len*</span><span class="sxs-lookup"><span data-stu-id="51355-113">*len*</span></span>  
 <span data-ttu-id="51355-114">Содержит указатель на переменную `int`, которая содержит длину имени параметра в байтах.</span><span class="sxs-lookup"><span data-stu-id="51355-114">Provides a pointer to an `int` variable that contains the length, in bytes, of the parameter name.</span></span> <span data-ttu-id="51355-115">Если параметр *len* равен NULL, то длина имени параметра удаленной хранимой процедуры не возвращается.</span><span class="sxs-lookup"><span data-stu-id="51355-115">If *len* is NULL, the length of the remote stored procedure parameter name is not returned.</span></span>  
  
## <a name="returns"></a><span data-ttu-id="51355-116">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="51355-116">Returns</span></span>  
 <span data-ttu-id="51355-117">Указатель на строку, заканчивающуюся нулевым символом, которая содержит имя параметра.</span><span class="sxs-lookup"><span data-stu-id="51355-117">A pointer to a null-terminated character string that contains the parameter name.</span></span> <span data-ttu-id="51355-118">Длина имени параметра хранится в *len*.</span><span class="sxs-lookup"><span data-stu-id="51355-118">The length of the parameter name is stored in *len*.</span></span> <span data-ttu-id="51355-119">Если параметра с номером *n* или удаленной хранимой процедуры не существует, то возвращается значение NULL, *len* получает значение -1 и отправляется информационное сообщение об ошибке.</span><span class="sxs-lookup"><span data-stu-id="51355-119">If there is no *n*th parameter or no remote stored procedure, it returns NULL, *len* is set to -1, and an informational error message is sent.</span></span> <span data-ttu-id="51355-120">Если имя параметра равно NULL, для *len* устанавливается значение 0 и возвращается пустая строка, заканчивающаяся нулевым символом.</span><span class="sxs-lookup"><span data-stu-id="51355-120">If the parameter name is NULL, *len* is set to 0 and a null-terminated empty string is returned.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="51355-121">Remarks</span><span class="sxs-lookup"><span data-stu-id="51355-121">Remarks</span></span>  
 <span data-ttu-id="51355-122">Эта функция возвращает имя параметра вызова удаленной хранимой процедуры.</span><span class="sxs-lookup"><span data-stu-id="51355-122">This function gets the name of a remote stored procedure call parameter.</span></span> <span data-ttu-id="51355-123">Когда удаленная хранимая процедура вызывается с параметрами, эти параметры могут быть переданы либо по имени, либо по позиции — без указания имени.</span><span class="sxs-lookup"><span data-stu-id="51355-123">When a remote stored procedure call is made with parameters, the parameters can be passed either by name or by position (unnamed).</span></span> <span data-ttu-id="51355-124">Если при вызове удаленной хранимой процедуры часть параметров передается по имени, а часть — по позиции, возникает ошибка.</span><span class="sxs-lookup"><span data-stu-id="51355-124">If the remote stored procedure call is made with some parameters passed by name and some passed by position, an error occurs.</span></span> <span data-ttu-id="51355-125">Обработчик SRV_RPC по-прежнему вызывается, однако он отображается так, как если бы не имел параметров, а функция **srv_rpcparams** возвращает 0.</span><span class="sxs-lookup"><span data-stu-id="51355-125">The SRV_RPC handler is still called, but it appears as if there were no parameters, and **srv_rpcparams** returns 0.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="51355-126">Необходимо тщательно просмотреть исходный код расширенных хранимых процедур и проверить скомпилированные библиотеки DLL перед их установкой на рабочий сервер.</span><span class="sxs-lookup"><span data-stu-id="51355-126">You should thoroughly review the source code of extended stored procedures, and you should test the compiled DLLs before you install them on a production server.</span></span> <span data-ttu-id="51355-127">Сведения о проверке безопасности см. на следующем [веб-сайте Майкрософт](https://go.microsoft.com/fwlink/?LinkID=54761&amp;clcid=0x409https://msdn.microsoft.com/security/).</span><span class="sxs-lookup"><span data-stu-id="51355-127">For information about security review and testing, see this [Microsoft Web site](https://go.microsoft.com/fwlink/?LinkID=54761&amp;clcid=0x409https://msdn.microsoft.com/security/).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="51355-128">См. также:</span><span class="sxs-lookup"><span data-stu-id="51355-128">See Also</span></span>  
 [<span data-ttu-id="51355-129">srv_rpcparams (интерфейс API расширенных хранимых процедур)</span><span class="sxs-lookup"><span data-stu-id="51355-129">srv_rpcparams &#40;Extended Stored Procedure API&#41;</span></span>](srv-rpcparams-extended-stored-procedure-api.md)  
  
  
