---
title: srv_paramstatus (интерфейс API расширенных хранимых процедур) | Документы Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: stored-procedures
ms.topic: reference
api_name:
- srv_paramstatus
api_location:
- opends60.dll
topic_type:
- apiref
dev_langs:
- C++
helpviewer_keywords:
- srv_paramstatus
ms.assetid: 86cecd45-0b09-42e9-8152-32a12a1c2b7a
author: rothja
ms.author: jroth
ms.openlocfilehash: d89d4ccbb6a97ff47669ad4ed9c0b4c22ac934eb
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87728241"
---
# <a name="srv_paramstatus-extended-stored-procedure-api"></a><span data-ttu-id="99bea-102">srv_paramstatus (API-интерфейс расширенных хранимых процедур)</span><span class="sxs-lookup"><span data-stu-id="99bea-102">srv_paramstatus (Extended Stored Procedure API)</span></span>
    
> [!IMPORTANT]  
>  [!INCLUDE[ssNoteDepFutureDontUse](../../includes/ssnotedepfuturedontuse-md.md)] <span data-ttu-id="99bea-103">Используйте вместо этого интеграцию со средой CLR.</span><span class="sxs-lookup"><span data-stu-id="99bea-103">Use CLR integration instead.</span></span>  
  
 <span data-ttu-id="99bea-104">Возвращает состояние параметра вызова определенной хранимой процедуры.</span><span class="sxs-lookup"><span data-stu-id="99bea-104">Returns the status of a particular remote stored procedure call parameter.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="99bea-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="99bea-105">Syntax</span></span>  
  
```  
  
int srv_paramstatus (  
SRV_PROC *  
srvproc  
,  
int  
n   
);  
  
```  
  
## <a name="arguments"></a><span data-ttu-id="99bea-106">Аргументы</span><span class="sxs-lookup"><span data-stu-id="99bea-106">Arguments</span></span>  
 <span data-ttu-id="99bea-107">*srvproc*</span><span class="sxs-lookup"><span data-stu-id="99bea-107">*srvproc*</span></span>  
 <span data-ttu-id="99bea-108">Указатель на структуру SRV_PROC, представляющую собой дескриптор соединения с клиентом (в данном случае — дескриптор, который получил вызов удаленной хранимой процедуры).</span><span class="sxs-lookup"><span data-stu-id="99bea-108">Is a pointer to the SRV_PROC structure that is the handle for a particular client connection (in this case, the handle that received the remote stored procedure call).</span></span> <span data-ttu-id="99bea-109">Эта структура содержит сведения, которые используются библиотекой API-интерфейса расширенных хранимых процедур для управления связью и передачи данных между приложением и клиентом.</span><span class="sxs-lookup"><span data-stu-id="99bea-109">The structure contains information the Extended Stored Procedure API library uses to manage communication and data between the application and the client.</span></span>  
  
 <span data-ttu-id="99bea-110">*n*</span><span class="sxs-lookup"><span data-stu-id="99bea-110">*n*</span></span>  
 <span data-ttu-id="99bea-111">Указывает номер параметра.</span><span class="sxs-lookup"><span data-stu-id="99bea-111">Indicates the number of the parameter.</span></span> <span data-ttu-id="99bea-112">Первый параметр имеет номер 1.</span><span class="sxs-lookup"><span data-stu-id="99bea-112">The first parameter is number 1.</span></span>  
  
## <a name="returns"></a><span data-ttu-id="99bea-113">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="99bea-113">Returns</span></span>  
 <span data-ttu-id="99bea-114">Целое число `int`, содержащее флаги состояния параметра.</span><span class="sxs-lookup"><span data-stu-id="99bea-114">An `int` that contains status flags for the parameter.</span></span> <span data-ttu-id="99bea-115">В данный момент существует только один флаг. Если биту 0 задано значение 1, этот параметр является возвращаемым параметром.</span><span class="sxs-lookup"><span data-stu-id="99bea-115">Currently, there is only one flag: If bit 0 is set to 1, the parameter is a return parameter.</span></span> <span data-ttu-id="99bea-116">Если отсутствует *n*-й параметр или удаленная хранимая процедура, то возвращается значение -1.</span><span class="sxs-lookup"><span data-stu-id="99bea-116">If there is no *n*th parameter or if there is no remote stored procedure, it returns -1.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="99bea-117">Remarks</span><span class="sxs-lookup"><span data-stu-id="99bea-117">Remarks</span></span>  
 <span data-ttu-id="99bea-118">Эта процедура возвращает флаги состояния для параметра вызова удаленной хранимой процедуры.</span><span class="sxs-lookup"><span data-stu-id="99bea-118">This routine returns the status flags for a remote stored procedure call parameter.</span></span>  
  
 <span data-ttu-id="99bea-119">Параметры содержат данные, передаваемые между клиентами и приложением с удаленной хранимой процедурой.</span><span class="sxs-lookup"><span data-stu-id="99bea-119">Parameters contain data passed between clients and the application with remote stored procedures.</span></span> <span data-ttu-id="99bea-120">Клиент может указать некоторые параметры в качестве возвращаемых.</span><span class="sxs-lookup"><span data-stu-id="99bea-120">The client can specify certain parameters as return parameters.</span></span> <span data-ttu-id="99bea-121">Эти возвращаемые параметры могут содержать значения, которые приложение передает обратно клиенту.</span><span class="sxs-lookup"><span data-stu-id="99bea-121">These return parameters can contain values that the application passes back to the client.</span></span>  
  
 <span data-ttu-id="99bea-122">В данный момент единственный флаг состояния — это флаг, указывающий на то, является ли данный параметр возвращаемым параметром.</span><span class="sxs-lookup"><span data-stu-id="99bea-122">Currently, the only status flag is one that indicates whether the parameter is a return parameter.</span></span>  
  
 <span data-ttu-id="99bea-123">Когда удаленная хранимая процедура вызывается с параметрами, эти параметры могут быть переданы либо по имени, либо по позиции — без указания имени.</span><span class="sxs-lookup"><span data-stu-id="99bea-123">When a remote stored procedure call is made with parameters, the parameters can be passed either by name or by position (unnamed).</span></span> <span data-ttu-id="99bea-124">Если при вызове удаленной хранимой процедуры часть параметров передается по имени, а часть — по позиции, возникает ошибка.</span><span class="sxs-lookup"><span data-stu-id="99bea-124">If the remote stored procedure call is made with some parameters passed by name and some passed by position, an error occurs.</span></span> <span data-ttu-id="99bea-125">Если возникает ошибка, обработчик SRV_RPC по-прежнему вызывается, но отображается так, как если бы параметры не существовали, а **srv_rpcparams** возвращает 0.</span><span class="sxs-lookup"><span data-stu-id="99bea-125">If an error occurs, the SRV_RPC handler is still called, but it appears as if there were no parameters, and **srv_rpcparams** returns 0.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="99bea-126">Необходимо тщательно просмотреть исходный код расширенных хранимых процедур и проверить скомпилированные библиотеки DLL перед их установкой на рабочий сервер.</span><span class="sxs-lookup"><span data-stu-id="99bea-126">You should thoroughly review the source code of extended stored procedures, and you should test the compiled DLLs before you install them on a production server.</span></span> <span data-ttu-id="99bea-127">Сведения о проверке безопасности см. на следующем [веб-сайте Майкрософт](https://go.microsoft.com/fwlink/?LinkID=54761&amp;clcid=0x409https://msdn.microsoft.com/security/).</span><span class="sxs-lookup"><span data-stu-id="99bea-127">For information about security review and testing, see this [Microsoft Web site](https://go.microsoft.com/fwlink/?LinkID=54761&amp;clcid=0x409https://msdn.microsoft.com/security/).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="99bea-128">См. также:</span><span class="sxs-lookup"><span data-stu-id="99bea-128">See Also</span></span>  
 [<span data-ttu-id="99bea-129">srv_rpcparams (интерфейс API расширенных хранимых процедур)</span><span class="sxs-lookup"><span data-stu-id="99bea-129">srv_rpcparams &#40;Extended Stored Procedure API&#41;</span></span>](srv-rpcparams-extended-stored-procedure-api.md)  
  
  
