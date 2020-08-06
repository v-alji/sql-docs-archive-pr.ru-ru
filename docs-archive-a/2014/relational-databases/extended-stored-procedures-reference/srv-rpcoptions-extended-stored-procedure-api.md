---
title: srv_rpcoptions (интерфейс API расширенных хранимых процедур) | Документы Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: stored-procedures
ms.topic: reference
api_name:
- srv_rpcoptions
api_location:
- opends60.dll
topic_type:
- apiref
dev_langs:
- C++
helpviewer_keywords:
- srv_rpcoptions
ms.assetid: dbcce5d1-d5a1-4379-9597-04e43af5923d
author: rothja
ms.author: jroth
ms.openlocfilehash: f5ebe4ab48721002e679ce149293b474a934e348
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87752147"
---
# <a name="srv_rpcoptions-extended-stored-procedure-api"></a><span data-ttu-id="0ac26-102">srv_rpcoptions (API-интерфейс расширенных хранимых процедур)</span><span class="sxs-lookup"><span data-stu-id="0ac26-102">srv_rpcoptions (Extended Stored Procedure API)</span></span>
    
> [!IMPORTANT]  
>  [!INCLUDE[ssNoteDepFutureDontUse](../../includes/ssnotedepfuturedontuse-md.md)] <span data-ttu-id="0ac26-103">Используйте вместо этого интеграцию со средой CLR.</span><span class="sxs-lookup"><span data-stu-id="0ac26-103">Use CLR integration instead.</span></span>  
  
 <span data-ttu-id="0ac26-104">Возвращает параметры времени выполнения для текущей удаленной хранимой процедуры.</span><span class="sxs-lookup"><span data-stu-id="0ac26-104">Returns run-time options for the current remote stored procedure.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0ac26-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="0ac26-105">Syntax</span></span>  
  
```  
  
DBUSMALLINT srv_rpcoptions ( SRV_PROC *  
srvproc   
);  
  
```  
  
## <a name="arguments"></a><span data-ttu-id="0ac26-106">Аргументы</span><span class="sxs-lookup"><span data-stu-id="0ac26-106">Arguments</span></span>  
 <span data-ttu-id="0ac26-107">*srvproc*</span><span class="sxs-lookup"><span data-stu-id="0ac26-107">*srvproc*</span></span>  
 <span data-ttu-id="0ac26-108">Указатель на структуру SRV_PROC, представляющую собой дескриптор соединения с клиентом (в данном случае — дескриптор, получивший удаленную хранимую процедуру).</span><span class="sxs-lookup"><span data-stu-id="0ac26-108">Is a pointer to the SRV_PROC structure that is the handle for a particular client connection (in this case, the handle that received the remote stored procedure).</span></span> <span data-ttu-id="0ac26-109">Эта структура содержит сведения, которые используются библиотекой API-интерфейса расширенных хранимых процедур для управления связью и передачи данных между приложением и клиентом.</span><span class="sxs-lookup"><span data-stu-id="0ac26-109">The structure contains information the Extended Stored Procedure API library uses to manage communication and data between the application and the client.</span></span>  
  
## <a name="returns"></a><span data-ttu-id="0ac26-110">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="0ac26-110">Returns</span></span>  
 <span data-ttu-id="0ac26-111">Битовая карта, которая содержит флаги времени выполнения, соединенные логической операцией ИЛИ для текущей удаленной хранимой процедуры.</span><span class="sxs-lookup"><span data-stu-id="0ac26-111">A bitmap that contains the run-time flags joined in a logical OR for the current remote stored procedure.</span></span> <span data-ttu-id="0ac26-112">При отсутствии текущей удаленной хранимой процедуры возвращается значение 0 и формируется сообщение.</span><span class="sxs-lookup"><span data-stu-id="0ac26-112">If there is not a current remote stored procedure, 0 is returned and a message is generated.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="0ac26-113">Remarks</span><span class="sxs-lookup"><span data-stu-id="0ac26-113">Remarks</span></span>  
 <span data-ttu-id="0ac26-114">В следующей таблице описывается каждый флаг времени выполнения.</span><span class="sxs-lookup"><span data-stu-id="0ac26-114">The following table describes each run-time flag.</span></span>  
  
|<span data-ttu-id="0ac26-115">Флаг времени выполнения</span><span class="sxs-lookup"><span data-stu-id="0ac26-115">Run-time flag</span></span>|<span data-ttu-id="0ac26-116">Описание</span><span class="sxs-lookup"><span data-stu-id="0ac26-116">Description</span></span>|  
|--------------------|-----------------|  
|<span data-ttu-id="0ac26-117">SRV_NOMETADATA</span><span class="sxs-lookup"><span data-stu-id="0ac26-117">SRV_NOMETADATA</span></span>|<span data-ttu-id="0ac26-118">Клиент запросил результаты без метаданных.</span><span class="sxs-lookup"><span data-stu-id="0ac26-118">The client has requested results without metadata information.</span></span> <span data-ttu-id="0ac26-119">Этот флаг используется только в том случае, если клиент взаимодействует с экземпляром [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="0ac26-119">This flag is only used when the client is communicating with an instance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="0ac26-120">Приложение API-интерфейса расширенных хранимых процедур не может исключить метаданные.</span><span class="sxs-lookup"><span data-stu-id="0ac26-120">An Extended Stored Procedure API application cannot omit metadata information.</span></span>|  
|<span data-ttu-id="0ac26-121">SRV_RECOMPILE</span><span class="sxs-lookup"><span data-stu-id="0ac26-121">SRV_RECOMPILE</span></span>|<span data-ttu-id="0ac26-122">Клиент запросил повторную компиляцию удаленной хранимой процедуры перед ее выполнением.</span><span class="sxs-lookup"><span data-stu-id="0ac26-122">The client has requested to recompile the remote stored procedure before executing it.</span></span> <span data-ttu-id="0ac26-123">Этот флаг не может применяться к приложению API-интерфейса расширенных хранимых процедур.</span><span class="sxs-lookup"><span data-stu-id="0ac26-123">This flag may not apply to an Extended Stored Procedure API application.</span></span>|  
  
> [!IMPORTANT]  
>  <span data-ttu-id="0ac26-124">Необходимо тщательно просмотреть исходный код расширенных хранимых процедур и проверить скомпилированные библиотеки DLL перед их установкой на рабочий сервер.</span><span class="sxs-lookup"><span data-stu-id="0ac26-124">You should thoroughly review the source code of extended stored procedures, and you should test the compiled DLLs before you install them on a production server.</span></span> <span data-ttu-id="0ac26-125">Сведения о проверке безопасности см. на следующем [веб-сайте Майкрософт](https://go.microsoft.com/fwlink/?LinkID=54761&amp;clcid=0x409https://msdn.microsoft.com/security/).</span><span class="sxs-lookup"><span data-stu-id="0ac26-125">For information about security review and testing, see this [Microsoft Web site](https://go.microsoft.com/fwlink/?LinkID=54761&amp;clcid=0x409https://msdn.microsoft.com/security/).</span></span>  
  
  
