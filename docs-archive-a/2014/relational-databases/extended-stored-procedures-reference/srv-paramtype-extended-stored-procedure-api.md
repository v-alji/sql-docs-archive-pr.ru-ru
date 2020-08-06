---
title: srv_paramtype (интерфейс API расширенных хранимых процедур) | Документы Майкрософт
ms.custom: ''
ms.date: 03/08/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: stored-procedures
ms.topic: reference
api_name:
- srv_paramtype
api_location:
- opends60.dll
topic_type:
- apiref
dev_langs:
- C++
helpviewer_keywords:
- srv_paramtype
ms.assetid: badc6d36-8a87-42b5-b28c-9c4f5ded8552
author: rothja
ms.author: jroth
ms.openlocfilehash: 0c4b4006f8214670e3bd2bddfbaabe917fb9d778
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87657106"
---
# <a name="srv_paramtype-extended-stored-procedure-api"></a><span data-ttu-id="ac561-102">srv_paramtype (API-интерфейс расширенных хранимых процедур)</span><span class="sxs-lookup"><span data-stu-id="ac561-102">srv_paramtype (Extended Stored Procedure API)</span></span>
    
> [!IMPORTANT]  
>  [!INCLUDE[ssNoteDepFutureDontUse](../../includes/ssnotedepfuturedontuse-md.md)] <span data-ttu-id="ac561-103">Используйте вместо этого интеграцию со средой CLR.</span><span class="sxs-lookup"><span data-stu-id="ac561-103">Use CLR integration instead.</span></span>  
  
 <span data-ttu-id="ac561-104">Возвращает тип данных параметра вызова удаленной хранимой процедуры.</span><span class="sxs-lookup"><span data-stu-id="ac561-104">Returns the data type of a remote stored procedure call parameter.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ac561-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="ac561-105">Syntax</span></span>  
  
```  
  
int srv_paramtype (  
SRV_PROC *  
srvproc  
,  
int  
n   
);  
  
```  
  
## <a name="arguments"></a><span data-ttu-id="ac561-106">Аргументы</span><span class="sxs-lookup"><span data-stu-id="ac561-106">Arguments</span></span>  
 <span data-ttu-id="ac561-107">*srvproc*</span><span class="sxs-lookup"><span data-stu-id="ac561-107">*srvproc*</span></span>  
 <span data-ttu-id="ac561-108">Указатель на структуру SRV_PROC, представляющую собой дескриптор соединения с клиентом (в данном случае — дескриптор, который получил вызов удаленной хранимой процедуры).</span><span class="sxs-lookup"><span data-stu-id="ac561-108">Is a pointer to the SRV_PROC structure that is the handle for a particular client connection (in this case, the handle that received the remote stored procedure call).</span></span> <span data-ttu-id="ac561-109">Эта структура содержит сведения, которые используются библиотекой API-интерфейса расширенных хранимых процедур для управления связью и передачи данных между приложением и клиентом.</span><span class="sxs-lookup"><span data-stu-id="ac561-109">The structure contains information the Extended Stored Procedure API library uses to manage communication and data between the application and the client.</span></span>  
  
 <span data-ttu-id="ac561-110">*n*</span><span class="sxs-lookup"><span data-stu-id="ac561-110">*n*</span></span>  
 <span data-ttu-id="ac561-111">Указывает номер параметра.</span><span class="sxs-lookup"><span data-stu-id="ac561-111">Indicates the number of the parameter.</span></span> <span data-ttu-id="ac561-112">Первый параметр имеет значение 1.</span><span class="sxs-lookup"><span data-stu-id="ac561-112">The first parameter is 1.</span></span>  
  
## <a name="returns"></a><span data-ttu-id="ac561-113">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="ac561-113">Returns</span></span>  
 <span data-ttu-id="ac561-114">Значение токена для типа данных параметра.</span><span class="sxs-lookup"><span data-stu-id="ac561-114">A token value for the data type of the parameter.</span></span> <span data-ttu-id="ac561-115">Сведения о типах данных см. в разделе [Типы данных (интерфейс API расширенных хранимых процедур)](data-types-extended-stored-procedure-api.md).</span><span class="sxs-lookup"><span data-stu-id="ac561-115">For information about data types, see [Data Types &#40;Extended Stored Procedure API&#41;](data-types-extended-stored-procedure-api.md).</span></span> <span data-ttu-id="ac561-116">Если параметра с номером *n* или удаленной хранимой процедуры не существует, возвращается значение - 1.</span><span class="sxs-lookup"><span data-stu-id="ac561-116">If there is no *n*th parameter or if there is no remote stored procedure, it returns - 1.</span></span>  
  
 <span data-ttu-id="ac561-117">Эта функция возвращает следующие значения, если параметр относится к одному из [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] типов данных.</span><span class="sxs-lookup"><span data-stu-id="ac561-117">This function returns the following values, if the parameter is one of the [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] data types.</span></span>  
  
|<span data-ttu-id="ac561-118">Новые типы данных</span><span class="sxs-lookup"><span data-stu-id="ac561-118">New data types</span></span>|<span data-ttu-id="ac561-119">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="ac561-119">Return value</span></span>|  
|--------------------|------------------|  
|`BITN`|<span data-ttu-id="ac561-120">SRVBIT</span><span class="sxs-lookup"><span data-stu-id="ac561-120">SRVBIT</span></span>|  
|`BIGVARCHAR`|<span data-ttu-id="ac561-121">VARCHAR</span><span class="sxs-lookup"><span data-stu-id="ac561-121">VARCHAR</span></span>|  
|`BIGCHAR`|<span data-ttu-id="ac561-122">CHAR</span><span class="sxs-lookup"><span data-stu-id="ac561-122">CHAR</span></span>|  
|`BIGBINARY`|<span data-ttu-id="ac561-123">BINARY</span><span class="sxs-lookup"><span data-stu-id="ac561-123">BINARY</span></span>|  
|`BIGVARBINARY`|<span data-ttu-id="ac561-124">VARBINARY</span><span class="sxs-lookup"><span data-stu-id="ac561-124">VARBINARY</span></span>|  
|`NCHAR`|<span data-ttu-id="ac561-125">CHAR</span><span class="sxs-lookup"><span data-stu-id="ac561-125">CHAR</span></span>|  
|`NVARCHAR`|<span data-ttu-id="ac561-126">VARCHAR</span><span class="sxs-lookup"><span data-stu-id="ac561-126">VARCHAR</span></span>|  
|`NTEXT`|<span data-ttu-id="ac561-127">-1</span><span class="sxs-lookup"><span data-stu-id="ac561-127">-1</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ac561-128">Remarks</span><span class="sxs-lookup"><span data-stu-id="ac561-128">Remarks</span></span>  
 <span data-ttu-id="ac561-129">Когда удаленная хранимая процедура вызывается с параметрами, эти параметры могут быть переданы либо по имени, либо по позиции — без указания имени.</span><span class="sxs-lookup"><span data-stu-id="ac561-129">When a remote stored procedure call is made with parameters, the parameters can be passed either by name or by position (unnamed).</span></span> <span data-ttu-id="ac561-130">Если при вызове удаленной хранимой процедуры часть параметров передается по имени, а часть — по позиции, возникает ошибка.</span><span class="sxs-lookup"><span data-stu-id="ac561-130">If the remote stored procedure call is made with some parameters passed by name and some passed by position, an error occurs.</span></span> <span data-ttu-id="ac561-131">Обработчик SRV_RPC по-прежнему вызывается, но он выглядит так, как если бы параметры не существовали, а **srv_rpcparams** возвращает 0.</span><span class="sxs-lookup"><span data-stu-id="ac561-131">The SRV_RPC handler is still called, but it appears as if there were no parameters and **srv_rpcparams** returns 0.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="ac561-132">Необходимо тщательно просмотреть исходный код расширенных хранимых процедур и проверить скомпилированные библиотеки DLL перед их установкой на рабочий сервер.</span><span class="sxs-lookup"><span data-stu-id="ac561-132">You should thoroughly review the source code of extended stored procedures, and you should test the compiled DLLs before you install them on a production server.</span></span> <span data-ttu-id="ac561-133">Сведения о проверке безопасности см. на следующем [веб-сайте Майкрософт](https://go.microsoft.com/fwlink/?LinkID=54761&amp;clcid=0x409https://msdn.microsoft.com/security/).</span><span class="sxs-lookup"><span data-stu-id="ac561-133">For information about security review and testing, see this [Microsoft Web site](https://go.microsoft.com/fwlink/?LinkID=54761&amp;clcid=0x409https://msdn.microsoft.com/security/).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ac561-134">См. также:</span><span class="sxs-lookup"><span data-stu-id="ac561-134">See Also</span></span>  
 <span data-ttu-id="ac561-135">[API srv_paraminfo &#40;расширенных хранимых процедур&#41;](srv-paraminfo-extended-stored-procedure-api.md) </span><span class="sxs-lookup"><span data-stu-id="ac561-135">[srv_paraminfo &#40;Extended Stored Procedure API&#41;](srv-paraminfo-extended-stored-procedure-api.md) </span></span>  
 [<span data-ttu-id="ac561-136">srv_rpcparams (интерфейс API расширенных хранимых процедур)</span><span class="sxs-lookup"><span data-stu-id="ac561-136">srv_rpcparams &#40;Extended Stored Procedure API&#41;</span></span>](srv-rpcparams-extended-stored-procedure-api.md)  
  
  
