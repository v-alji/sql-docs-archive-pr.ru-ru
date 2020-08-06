---
title: srv_paramnumber (интерфейс API расширенных хранимых процедур) | Документы Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: stored-procedures
ms.topic: reference
api_name:
- srv_paramnumber
api_location:
- opends60.dll
topic_type:
- apiref
dev_langs:
- C++
helpviewer_keywords:
- srv_paramnumber
ms.assetid: d7a6dbff-71d9-4297-8a4f-bfd2876fe204
author: rothja
ms.author: jroth
ms.openlocfilehash: 1e621101c909ef251c40f38713e438d8e40d08a9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87666607"
---
# <a name="srv_paramnumber-extended-stored-procedure-api"></a><span data-ttu-id="7f85e-102">srv_paramnumber (API-интерфейс расширенных хранимых процедур)</span><span class="sxs-lookup"><span data-stu-id="7f85e-102">srv_paramnumber (Extended Stored Procedure API)</span></span>
    
> [!IMPORTANT]  
>  [!INCLUDE[ssNoteDepFutureDontUse](../../includes/ssnotedepfuturedontuse-md.md)] <span data-ttu-id="7f85e-103">Используйте вместо этого интеграцию со средой CLR.</span><span class="sxs-lookup"><span data-stu-id="7f85e-103">Use CLR integration instead.</span></span>  
  
 <span data-ttu-id="7f85e-104">Возвращает номер параметра вызова удаленной хранимой процедуры.</span><span class="sxs-lookup"><span data-stu-id="7f85e-104">Returns the number of a remote stored procedure call parameter.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7f85e-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="7f85e-105">Syntax</span></span>  
  
```  
  
int srv_paramnumber (  
SRV_PROC *  
srvproc  
,  
DBCHAR *  
name  
,   
int  
namelen   
);  
  
```  
  
## <a name="arguments"></a><span data-ttu-id="7f85e-106">Аргументы</span><span class="sxs-lookup"><span data-stu-id="7f85e-106">Arguments</span></span>  
 <span data-ttu-id="7f85e-107">*srvproc*</span><span class="sxs-lookup"><span data-stu-id="7f85e-107">*srvproc*</span></span>  
 <span data-ttu-id="7f85e-108">Указатель на структуру SRV_PROC, представляющую собой дескриптор соединения с клиентом (в данном случае — дескриптор, который получил вызов удаленной хранимой процедуры).</span><span class="sxs-lookup"><span data-stu-id="7f85e-108">Is a pointer to the SRV_PROC structure that is the handle for a particular client connection (in this case, the handle that received the remote stored procedure call).</span></span> <span data-ttu-id="7f85e-109">Эта структура содержит сведения, которые используются библиотекой API-интерфейса расширенных хранимых процедур для управления связью и передачи данных между приложением и клиентом.</span><span class="sxs-lookup"><span data-stu-id="7f85e-109">The structure contains information the Extended Stored Procedure API library uses to manage communication and data between the application and the client.</span></span>  
  
 <span data-ttu-id="7f85e-110">*name*</span><span class="sxs-lookup"><span data-stu-id="7f85e-110">*name*</span></span>  
 <span data-ttu-id="7f85e-111">Указатель на параметр *name*.</span><span class="sxs-lookup"><span data-stu-id="7f85e-111">Is a pointer to the parameter *name*.</span></span>  
  
 <span data-ttu-id="7f85e-112">*namelen*</span><span class="sxs-lookup"><span data-stu-id="7f85e-112">*namelen*</span></span>  
 <span data-ttu-id="7f85e-113">Длина параметра *name*.</span><span class="sxs-lookup"><span data-stu-id="7f85e-113">Is the length of *name*.</span></span> <span data-ttu-id="7f85e-114">Если *name* заканчивается нулевым байтом, задайте для параметра *namelen* значение SRV_NULLTERM.</span><span class="sxs-lookup"><span data-stu-id="7f85e-114">If *name* is null-terminated, set *namelen* to SRV_NULLTERM.</span></span>  
  
## <a name="returns"></a><span data-ttu-id="7f85e-115">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="7f85e-115">Returns</span></span>  
 <span data-ttu-id="7f85e-116">Номер параметра именованного параметра.</span><span class="sxs-lookup"><span data-stu-id="7f85e-116">The parameter number of the named parameter.</span></span> <span data-ttu-id="7f85e-117">Первый параметр имеет значение 1.</span><span class="sxs-lookup"><span data-stu-id="7f85e-117">The first parameter is 1.</span></span> <span data-ttu-id="7f85e-118">При отсутствии параметра с именем *name* или при отсутствии удаленной хранимой процедуры возвращается значение 0 и формируется сообщение.</span><span class="sxs-lookup"><span data-stu-id="7f85e-118">If there is no parameter named *name* or no remote stored procedure, 0 is returned and a message is generated.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="7f85e-119">Remarks</span><span class="sxs-lookup"><span data-stu-id="7f85e-119">Remarks</span></span>  
 <span data-ttu-id="7f85e-120">Когда удаленная хранимая процедура вызывается с параметрами, эти параметры могут быть переданы либо по имени, либо по позиции — без указания имени.</span><span class="sxs-lookup"><span data-stu-id="7f85e-120">When a remote stored procedure call is made with parameters, the parameters can be passed either by name or by position (unnamed).</span></span> <span data-ttu-id="7f85e-121">Если при вызове удаленной хранимой процедуры часть параметров передается по имени, а часть — по позиции, возникает ошибка.</span><span class="sxs-lookup"><span data-stu-id="7f85e-121">If the remote stored procedure call is made with some parameters passed by name and some passed by position, an error occurs.</span></span> <span data-ttu-id="7f85e-122">Обработчик SRV_RPC по-прежнему вызывается, однако он отображается так, как если бы не имел параметров, а функция **srv_rpcparams** возвращает 0.</span><span class="sxs-lookup"><span data-stu-id="7f85e-122">The SRV_RPC handler is still called, but it appears as if there were no parameters, and **srv_rpcparams** returns 0.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="7f85e-123">Необходимо тщательно просмотреть исходный код расширенных хранимых процедур и проверить скомпилированные библиотеки DLL перед их установкой на рабочий сервер.</span><span class="sxs-lookup"><span data-stu-id="7f85e-123">You should thoroughly review the source code of extended stored procedures, and you should test the compiled DLLs before you install them on a production server.</span></span> <span data-ttu-id="7f85e-124">Сведения о проверке безопасности см. на следующем [веб-сайте Майкрософт](https://go.microsoft.com/fwlink/?LinkID=54761&amp;clcid=0x409https://msdn.microsoft.com/security/).</span><span class="sxs-lookup"><span data-stu-id="7f85e-124">For information about security review and testing, see this [Microsoft Web site](https://go.microsoft.com/fwlink/?LinkID=54761&amp;clcid=0x409https://msdn.microsoft.com/security/).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7f85e-125">См. также:</span><span class="sxs-lookup"><span data-stu-id="7f85e-125">See Also</span></span>  
 [<span data-ttu-id="7f85e-126">srv_rpcparams (интерфейс API расширенных хранимых процедур)</span><span class="sxs-lookup"><span data-stu-id="7f85e-126">srv_rpcparams &#40;Extended Stored Procedure API&#41;</span></span>](srv-rpcparams-extended-stored-procedure-api.md)  
  
  
