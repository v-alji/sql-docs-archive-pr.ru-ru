---
title: srv_rpcparams (интерфейс API расширенных хранимых процедур) | Документы Майкрософт
ms.custom: ''
ms.date: 04/27/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: stored-procedures
ms.topic: reference
api_name:
- srv_rpcparams
api_location:
- opends60.dll
topic_type:
- apiref
dev_langs:
- C++
helpviewer_keywords:
- srv_rpcparams
ms.assetid: 96a5e6f6-d320-4623-b96e-0a856e3abebb
author: rothja
ms.author: jroth
ms.openlocfilehash: 443b9ea8a67341afdb92f0c384148c8b1b42f752
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87752139"
---
# <a name="srv_rpcparams-extended-stored-procedure-api"></a><span data-ttu-id="13d75-102">srv_rpcparams (API-интерфейс расширенных хранимых процедур)</span><span class="sxs-lookup"><span data-stu-id="13d75-102">srv_rpcparams (Extended Stored Procedure API)</span></span>
    
> [!IMPORTANT]  
>  [!INCLUDE[ssNoteDepFutureDontUse](../../includes/ssnotedepfuturedontuse-md.md)] <span data-ttu-id="13d75-103">Используйте вместо этого интеграцию со средой CLR.</span><span class="sxs-lookup"><span data-stu-id="13d75-103">Use CLR integration instead.</span></span>  
  
 <span data-ttu-id="13d75-104">Возвращает количество параметров для текущей удаленной хранимой процедуры.</span><span class="sxs-lookup"><span data-stu-id="13d75-104">Returns the number of parameters for the current remote stored procedure.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="13d75-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="13d75-105">Syntax</span></span>  
  
```  
  
int srv_rpcparams ( SRV_PROC *  
srvproc   
);  
  
```  
  
## <a name="arguments"></a><span data-ttu-id="13d75-106">Аргументы</span><span class="sxs-lookup"><span data-stu-id="13d75-106">Arguments</span></span>  
 <span data-ttu-id="13d75-107">*srvproc*</span><span class="sxs-lookup"><span data-stu-id="13d75-107">*srvproc*</span></span>  
 <span data-ttu-id="13d75-108">Указатель на структуру SRV_PROC, представляющую собой дескриптор соединения с клиентом (в данном случае — дескриптор, получивший удаленную хранимую процедуру).</span><span class="sxs-lookup"><span data-stu-id="13d75-108">Is a pointer to the SRV_PROC structure that is the handle for a particular client connection (in this case, the handle that received the remote stored procedure).</span></span> <span data-ttu-id="13d75-109">Структура содержит сведения, которые используются библиотекой API-интерфейса расширенных хранимых процедур для управления связью и передачи данных между приложением и клиентом.</span><span class="sxs-lookup"><span data-stu-id="13d75-109">The structure contains information that the Extended Stored Procedure API library uses to manage communication and data between the application and the client.</span></span>  
  
## <a name="returns"></a><span data-ttu-id="13d75-110">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="13d75-110">Returns</span></span>  
 <span data-ttu-id="13d75-111">Количество параметров удаленной хранимой процедуры.</span><span class="sxs-lookup"><span data-stu-id="13d75-111">The number of parameters in the remote stored procedure.</span></span> <span data-ttu-id="13d75-112">Если удаленная хранимая процедура не имеет параметров или отсутствует текущая удаленная хранимая процедура, то возвращается значение -1 и возникает информационная ошибка.</span><span class="sxs-lookup"><span data-stu-id="13d75-112">If there are no parameters in the remote stored procedure or if there is not a current remote stored procedure, -1 is returned and an information error occurs.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="13d75-113">Remarks</span><span class="sxs-lookup"><span data-stu-id="13d75-113">Remarks</span></span>  
 <span data-ttu-id="13d75-114">Эта функция возвращает количество параметров текущей удаленной хранимой процедуры.</span><span class="sxs-lookup"><span data-stu-id="13d75-114">This function returns the number of parameters in the current remote stored procedure.</span></span> <span data-ttu-id="13d75-115">Обычно она вызывается из удаленной хранимой процедуры.</span><span class="sxs-lookup"><span data-stu-id="13d75-115">It is usually called from the remote stored procedure.</span></span>  
  
 <span data-ttu-id="13d75-116">Когда удаленная хранимая процедура вызывается с параметрами, эти параметры могут быть переданы либо по имени, либо по позиции — без указания имени.</span><span class="sxs-lookup"><span data-stu-id="13d75-116">When a remote stored procedure call is made with parameters, the parameters can be passed either by name or by position (unnamed).</span></span> <span data-ttu-id="13d75-117">Если при вызове удаленной хранимой процедуры часть параметров была передана по имени, а часть — по позиции, то возникнет ошибка.</span><span class="sxs-lookup"><span data-stu-id="13d75-117">If the remote stored procedure call was made with some parameters passed by name and some passed by position, an error occurs.</span></span> <span data-ttu-id="13d75-118">В этом случае будет вызван обработчик удаленной хранимой процедуры, однако он не получает параметры, и **srv_rpcparams** вернет значение 0.</span><span class="sxs-lookup"><span data-stu-id="13d75-118">When this error occurs, the remote stored procedure handler is called, but it does not receive the parameters and **srv_rpcparams** returns 0.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="13d75-119">Необходимо тщательно просмотреть исходный код расширенных хранимых процедур и проверить скомпилированные библиотеки DLL перед их установкой на рабочий сервер.</span><span class="sxs-lookup"><span data-stu-id="13d75-119">You should thoroughly review the source code of extended stored procedures, and you should test the compiled DLLs before you install them on a production server.</span></span> <span data-ttu-id="13d75-120">Сведения о проверке безопасности см. на следующем [веб-сайте Майкрософт](https://go.microsoft.com/fwlink/?LinkID=54761&amp;clcid=0x409https://msdn.microsoft.com/security/).</span><span class="sxs-lookup"><span data-stu-id="13d75-120">For information about security review and testing, see this [Microsoft Web site](https://go.microsoft.com/fwlink/?LinkID=54761&amp;clcid=0x409https://msdn.microsoft.com/security/).</span></span>  
  
  
