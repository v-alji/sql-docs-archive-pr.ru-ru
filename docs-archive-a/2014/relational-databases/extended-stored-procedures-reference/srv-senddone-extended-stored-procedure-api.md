---
title: srv_senddone (интерфейс API расширенных хранимых процедур) | Документы Майкрософт
ms.custom: ''
ms.date: 04/27/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: stored-procedures
ms.topic: reference
api_name:
- srv_senddone
api_location:
- opends60.dll
topic_type:
- apiref
dev_langs:
- C++
helpviewer_keywords:
- srv_senddone
ms.assetid: 1fc4f1d5-56d4-43f6-b5e4-0c0cc295cba3
author: rothja
ms.author: jroth
ms.openlocfilehash: 877acdc1b666c7f4cbaab737590a1c55e474eb05
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87752136"
---
# <a name="srv_senddone-extended-stored-procedure-api"></a><span data-ttu-id="82c20-102">srv_senddone (API-интерфейс расширенных хранимых процедур)</span><span class="sxs-lookup"><span data-stu-id="82c20-102">srv_senddone (Extended Stored Procedure API)</span></span>
    
> [!IMPORTANT]  
>  [!INCLUDE[ssNoteDepFutureDontUse](../../includes/ssnotedepfuturedontuse-md.md)] <span data-ttu-id="82c20-103">Используйте вместо этого интеграцию со средой CLR.</span><span class="sxs-lookup"><span data-stu-id="82c20-103">Use CLR integration instead.</span></span>  
  
 <span data-ttu-id="82c20-104">Передает клиенту сообщение о результатах завершения.</span><span class="sxs-lookup"><span data-stu-id="82c20-104">Sends a result completion message to the client.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="82c20-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="82c20-105">Syntax</span></span>  
  
```  
  
int srv_senddone (  
SRV_PROC *  
srvproc  
,  
DBUSMALLINT   
status  
,  
DBUSMALLINT  
info  
,  
DBINT  
count   
);  
  
```  
  
## <a name="arguments"></a><span data-ttu-id="82c20-106">Аргументы</span><span class="sxs-lookup"><span data-stu-id="82c20-106">Arguments</span></span>  
 <span data-ttu-id="82c20-107">*srvproc*</span><span class="sxs-lookup"><span data-stu-id="82c20-107">*srvproc*</span></span>  
 <span data-ttu-id="82c20-108">Указатель на структуру SRV_PROC, который представляет собой дескриптор соединения с клиентом (в данном случае — дескриптор, который получил запрос языка).</span><span class="sxs-lookup"><span data-stu-id="82c20-108">Is a pointer to the SRV_PROC structure that is the handle for a particular client connection (in this case, the handle that received the language request).</span></span> <span data-ttu-id="82c20-109">Структура содержит сведения, которые используются библиотекой API-интерфейса расширенных хранимых процедур для управления связью и передачи данных между приложением и клиентом.</span><span class="sxs-lookup"><span data-stu-id="82c20-109">The structure contains information that the Extended Stored Procedure API library uses to manage communication and data between the application and the client.</span></span>  
  
 <span data-ttu-id="82c20-110">*status*</span><span class="sxs-lookup"><span data-stu-id="82c20-110">*status*</span></span>  
 <span data-ttu-id="82c20-111">Представляет собой двухбайтовое поле для различных флагов *status* .</span><span class="sxs-lookup"><span data-stu-id="82c20-111">Is a 2-byte field for various *status* flags.</span></span> <span data-ttu-id="82c20-112">С помощью логических операторов И и ИЛИ можно задавать сразу несколько флагов *status* .</span><span class="sxs-lookup"><span data-stu-id="82c20-112">Multiple flags can be set by using the AND and OR logical operators with *status* flag values.</span></span> <span data-ttu-id="82c20-113">В следующей таблице перечислены возможные флаги *status* .</span><span class="sxs-lookup"><span data-stu-id="82c20-113">The following table lists possible *status* flags.</span></span>  
  
|<span data-ttu-id="82c20-114">Флаг состояния</span><span class="sxs-lookup"><span data-stu-id="82c20-114">Status flag</span></span>|<span data-ttu-id="82c20-115">Описание</span><span class="sxs-lookup"><span data-stu-id="82c20-115">Description</span></span>|  
|-----------------|-----------------|  
|<span data-ttu-id="82c20-116">SRV_DONE_COUNT</span><span class="sxs-lookup"><span data-stu-id="82c20-116">SRV_DONE_COUNT</span></span>|<span data-ttu-id="82c20-117">Параметр *count* содержит допустимое значение счетчика.</span><span class="sxs-lookup"><span data-stu-id="82c20-117">The *count* parameter contains a valid count.</span></span>|  
|<span data-ttu-id="82c20-118">SRV_DONE_ERROR</span><span class="sxs-lookup"><span data-stu-id="82c20-118">SRV_DONE_ERROR</span></span>|<span data-ttu-id="82c20-119">Текущая клиентская команда получила ошибку.</span><span class="sxs-lookup"><span data-stu-id="82c20-119">The current client command received an error.</span></span>|  
  
 <span data-ttu-id="82c20-120">*сведения*</span><span class="sxs-lookup"><span data-stu-id="82c20-120">*info*</span></span>  
 <span data-ttu-id="82c20-121">Зарезервированное поле длиной 2 байта.</span><span class="sxs-lookup"><span data-stu-id="82c20-121">Is a reserved, 2-byte field.</span></span> <span data-ttu-id="82c20-122">Присвойте этому параметру значение 0.</span><span class="sxs-lookup"><span data-stu-id="82c20-122">Set this value to 0.</span></span>  
  
 <span data-ttu-id="82c20-123">*count*</span><span class="sxs-lookup"><span data-stu-id="82c20-123">*count*</span></span>  
 <span data-ttu-id="82c20-124">Поле размером 4 байта, используемое как счетчик текущего результирующего набора.</span><span class="sxs-lookup"><span data-stu-id="82c20-124">Is a 4-byte field used to indicate a count for the current result set.</span></span> <span data-ttu-id="82c20-125">Если в поле *status* установлен флаг SRV_DONE_COUNT, поле *count* содержит допустимое значение счетчика.</span><span class="sxs-lookup"><span data-stu-id="82c20-125">If the SRV_DONE_COUNT flag is set in the *status* field, *count* holds a valid count.</span></span>  
  
## <a name="returns"></a><span data-ttu-id="82c20-126">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="82c20-126">Returns</span></span>  
 <span data-ttu-id="82c20-127">SUCCEED или FAIL</span><span class="sxs-lookup"><span data-stu-id="82c20-127">SUCCEED or FAIL</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="82c20-128">Remarks</span><span class="sxs-lookup"><span data-stu-id="82c20-128">Remarks</span></span>  
 <span data-ttu-id="82c20-129">По запросу клиента сервер может выполнить ряд команд и вернуть несколько результирующих наборов.</span><span class="sxs-lookup"><span data-stu-id="82c20-129">A client request can cause the server to execute a number of commands and to return a number of result sets.</span></span> <span data-ttu-id="82c20-130">Для каждого результирующего набора функция **srv_senddone** должна вернуть клиенту сообщение о завершении с результатом.</span><span class="sxs-lookup"><span data-stu-id="82c20-130">For each result set, **srv_senddone** must return a result completion message to the client.</span></span>  
  
 <span data-ttu-id="82c20-131">Поле *count* указывает количество строк, затронутых командой.</span><span class="sxs-lookup"><span data-stu-id="82c20-131">The *count* field indicates the number of rows affected by a command.</span></span> <span data-ttu-id="82c20-132">Если в поле *count* содержится значение счетчика, то в поле *status* должен быть установлен флаг SRV_DONE_COUNT.</span><span class="sxs-lookup"><span data-stu-id="82c20-132">If the *count* field contains a count, the SRV_DONE_COUNT flag should be set in the *status* field.</span></span> <span data-ttu-id="82c20-133">Это значение позволяет клиенту провести различие между значением *count* (равным 0) и неиспользуемым полем *count* .</span><span class="sxs-lookup"><span data-stu-id="82c20-133">This setting allows the client to distinguish between a *count* value of 0 and an unused *count* field.</span></span>  
  
 <span data-ttu-id="82c20-134">Нельзя вызывать функцию **srv_senddone** из обработчика SRV_CONNECT.</span><span class="sxs-lookup"><span data-stu-id="82c20-134">Do not call **srv_senddone** from the SRV_CONNECT handler.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="82c20-135">Необходимо тщательно просмотреть исходный код расширенных хранимых процедур и проверить скомпилированные библиотеки DLL перед их установкой на рабочий сервер.</span><span class="sxs-lookup"><span data-stu-id="82c20-135">You should thoroughly review the source code of extended stored procedures, and you should test the compiled DLLs before you install them on a production server.</span></span> <span data-ttu-id="82c20-136">Сведения о проверке безопасности см. на следующем [веб-сайте Майкрософт](https://go.microsoft.com/fwlink/?LinkID=54761&amp;clcid=0x409https://msdn.microsoft.com/security/).</span><span class="sxs-lookup"><span data-stu-id="82c20-136">For information about security review and testing, see this [Microsoft Web site](https://go.microsoft.com/fwlink/?LinkID=54761&amp;clcid=0x409https://msdn.microsoft.com/security/).</span></span>  
  
  
