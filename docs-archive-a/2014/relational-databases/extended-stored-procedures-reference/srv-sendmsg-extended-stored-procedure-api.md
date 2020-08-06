---
title: srv_sendmsg (интерфейс API расширенных хранимых процедур) | Документы Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: stored-procedures
ms.topic: reference
api_name:
- srv_sendmsg
api_location:
- opends60.dll
topic_type:
- apiref
dev_langs:
- C++
helpviewer_keywords:
- srv_sendmsg
ms.assetid: efcb50b9-f8ff-4121-bf67-05830171b928
author: rothja
ms.author: jroth
ms.openlocfilehash: 0821ad88f48313cfadea634a489def9b242a49f0
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87752132"
---
# <a name="srv_sendmsg-extended-stored-procedure-api"></a><span data-ttu-id="75fa2-102">srv_sendmsg (API-интерфейс расширенных хранимых процедур)</span><span class="sxs-lookup"><span data-stu-id="75fa2-102">srv_sendmsg (Extended Stored Procedure API)</span></span>
    
> [!IMPORTANT]  
>  [!INCLUDE[ssNoteDepFutureDontUse](../../includes/ssnotedepfuturedontuse-md.md)] <span data-ttu-id="75fa2-103">Используйте вместо этого интеграцию со средой CLR.</span><span class="sxs-lookup"><span data-stu-id="75fa2-103">Use CLR integration instead.</span></span>  
  
 <span data-ttu-id="75fa2-104">Отправляет клиенту сообщение.</span><span class="sxs-lookup"><span data-stu-id="75fa2-104">Sends a message to the client.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="75fa2-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="75fa2-105">Syntax</span></span>  
  
```  
  
int srv_sendmsg (  
SRV_PROC *  
srvproc  
,  
int  
msgtype  
,  
DBINT  
msgnum  
,  
DBTINYINT  
class  
,   
DBTINYINT  
state  
,  
DBCHAR *  
rpcname  
,  
int   
rpcnamelen  
,  
DBUSMALLINT  
linenum  
,  
DBCHAR *  
message  
,  
int  
msglen   
);  
  
```  
  
## <a name="arguments"></a><span data-ttu-id="75fa2-106">Аргументы</span><span class="sxs-lookup"><span data-stu-id="75fa2-106">Arguments</span></span>  
 <span data-ttu-id="75fa2-107">*srvproc*</span><span class="sxs-lookup"><span data-stu-id="75fa2-107">*srvproc*</span></span>  
 <span data-ttu-id="75fa2-108">Указатель на структуру SRV_PROC, который представляет собой дескриптор соединения с клиентом (в данном случае — дескриптор, который получил запрос языка).</span><span class="sxs-lookup"><span data-stu-id="75fa2-108">Is a pointer to the SRV_PROC structure that is the handle for a particular client connection (in this case, the handle that received the language request).</span></span> <span data-ttu-id="75fa2-109">Структура содержит сведения, которые используются библиотекой API-интерфейса расширенных хранимых процедур для управления связью и передачи данных между приложением и клиентом.</span><span class="sxs-lookup"><span data-stu-id="75fa2-109">The structure contains information that the Extended Stored Procedure API library uses to manage communication and data between the application and the client.</span></span>  
  
 <span data-ttu-id="75fa2-110">*msgtype*</span><span class="sxs-lookup"><span data-stu-id="75fa2-110">*msgtype*</span></span>  
 <span data-ttu-id="75fa2-111">Является либо SRV_MSG_INFO, либо SRV_MSG_ERROR, в зависимости от того, отправляет сервер информационное сообщение или сообщение об ошибке.</span><span class="sxs-lookup"><span data-stu-id="75fa2-111">Is either SRV_MSG_INFO or SRV_MSG_ERROR, depending on whether the server is sending an informational or error message.</span></span>  
  
 <span data-ttu-id="75fa2-112">*msgnum*</span><span class="sxs-lookup"><span data-stu-id="75fa2-112">*msgnum*</span></span>  
 <span data-ttu-id="75fa2-113">4-байтовый номер сообщения.</span><span class="sxs-lookup"><span data-stu-id="75fa2-113">Is a 4-byte message number.</span></span>  
  
 <span data-ttu-id="75fa2-114">*class*</span><span class="sxs-lookup"><span data-stu-id="75fa2-114">*class*</span></span>  
 <span data-ttu-id="75fa2-115">Указывает серьезность ошибки.</span><span class="sxs-lookup"><span data-stu-id="75fa2-115">Specifies the error severity.</span></span> <span data-ttu-id="75fa2-116">Серьезность, меньше или равная 10, считается информационным сообщением.</span><span class="sxs-lookup"><span data-stu-id="75fa2-116">A severity less than or equal to 10 is considered an informational message.</span></span>  
  
 <span data-ttu-id="75fa2-117">*state*</span><span class="sxs-lookup"><span data-stu-id="75fa2-117">*state*</span></span>  
 <span data-ttu-id="75fa2-118">Предоставляет код состояния ошибки для текущего сообщения.</span><span class="sxs-lookup"><span data-stu-id="75fa2-118">Provides the error state number for the current message.</span></span> <span data-ttu-id="75fa2-119">Код состояния ошибки предоставляет информацию о контексте ошибки.</span><span class="sxs-lookup"><span data-stu-id="75fa2-119">The error state number provides information about the context of the error.</span></span> <span data-ttu-id="75fa2-120">Допустимые значения кода состояния — от 0 до 255.</span><span class="sxs-lookup"><span data-stu-id="75fa2-120">Valid state numbers are from 0 through 255.</span></span>  
  
 <span data-ttu-id="75fa2-121">*rpcname*</span><span class="sxs-lookup"><span data-stu-id="75fa2-121">*rpcname*</span></span>  
 <span data-ttu-id="75fa2-122">Не поддерживается в текущей версии.</span><span class="sxs-lookup"><span data-stu-id="75fa2-122">Is currently not supported.</span></span>  
  
 <span data-ttu-id="75fa2-123">*rpcnamelen*</span><span class="sxs-lookup"><span data-stu-id="75fa2-123">*rpcnamelen*</span></span>  
 <span data-ttu-id="75fa2-124">Не поддерживается в текущей версии.</span><span class="sxs-lookup"><span data-stu-id="75fa2-124">Is currently not supported.</span></span>  
  
 <span data-ttu-id="75fa2-125">*линенум*</span><span class="sxs-lookup"><span data-stu-id="75fa2-125">*linenum*</span></span>  
 <span data-ttu-id="75fa2-126">Представляет собой номер строки в пакете языковых команд, к которому относится сообщение.</span><span class="sxs-lookup"><span data-stu-id="75fa2-126">Is the line number in the language command batch where the message applies.</span></span> <span data-ttu-id="75fa2-127">Номера строк начинаются с 1.</span><span class="sxs-lookup"><span data-stu-id="75fa2-127">Line numbers start at 1.</span></span> <span data-ttu-id="75fa2-128">Если параметр *linenum* не применяется к сообщению, установите его равным 0.</span><span class="sxs-lookup"><span data-stu-id="75fa2-128">If *linenum* does not apply to the message, set to 0.</span></span>  
  
 <span data-ttu-id="75fa2-129">*message*</span><span class="sxs-lookup"><span data-stu-id="75fa2-129">*message*</span></span>  
 <span data-ttu-id="75fa2-130">Является указателем на символьную строку, которая должна быть отправлена клиенту.</span><span class="sxs-lookup"><span data-stu-id="75fa2-130">Is a pointer to the character string to be sent to the client.</span></span>  
  
 <span data-ttu-id="75fa2-131">*msglen*</span><span class="sxs-lookup"><span data-stu-id="75fa2-131">*msglen*</span></span>  
 <span data-ttu-id="75fa2-132">Задает длину *message* в байтах.</span><span class="sxs-lookup"><span data-stu-id="75fa2-132">Specifies the length, in bytes, of *message*.</span></span> <span data-ttu-id="75fa2-133">Если *message*заканчивается нулевым байтом, задайте для параметра *msglen* значение SRV_NULLTERM.</span><span class="sxs-lookup"><span data-stu-id="75fa2-133">If *message* is null-terminated, set *msglen* to SRV_NULLTERM.</span></span>  
  
## <a name="returns"></a><span data-ttu-id="75fa2-134">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="75fa2-134">Returns</span></span>  
 <span data-ttu-id="75fa2-135">SUCCEED или FAIL</span><span class="sxs-lookup"><span data-stu-id="75fa2-135">SUCCEED or FAIL</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="75fa2-136">Remarks</span><span class="sxs-lookup"><span data-stu-id="75fa2-136">Remarks</span></span>  
 <span data-ttu-id="75fa2-137">Эта функция отправляет клиенту сообщение об ошибке или информационное сообщение.</span><span class="sxs-lookup"><span data-stu-id="75fa2-137">This function sends error or informational messages to the client.</span></span> <span data-ttu-id="75fa2-138">Она вызывается один раз для каждой отправки сообщения.</span><span class="sxs-lookup"><span data-stu-id="75fa2-138">It is called once for each message to be sent.</span></span>  
  
 <span data-ttu-id="75fa2-139">Можно отправлять сообщения клиенту при помощи функции **srv_sendmsg** в любой последовательности перед тем или после того, как были отправлены все строки (если таковые были) при помощи функции **srv_sendrow**.</span><span class="sxs-lookup"><span data-stu-id="75fa2-139">Messages can be sent to the client with **srv_sendmsg** in any order before or after all rows (if any) have been sent with **srv_sendrow**.</span></span> <span data-ttu-id="75fa2-140">Все сообщения, если таковые имеются, должны быть отправлены клиенту перед тем, как функция **srv_senddone** отправит состояние завершения.</span><span class="sxs-lookup"><span data-stu-id="75fa2-140">All messages, if any, must be sent to the client before the completion status is sent with **srv_senddone**.</span></span>  
  
 <span data-ttu-id="75fa2-141">Для отправки сообщений в Юникоде лучше использовать функцию **srv_wsendmsg**, чем функцию\*\* srv_sendmsg\*\*.</span><span class="sxs-lookup"><span data-stu-id="75fa2-141">To send messages in Unicode, use **srv_wsendmsg** rather than **srv_sendmsg**.</span></span>  
  
 <span data-ttu-id="75fa2-142">Дополнительные сведения см. в статье [Данные в Юникоде и кодовые страницы сервера](../extended-stored-procedures-programming/unicode-data-and-server-code-pages.md).</span><span class="sxs-lookup"><span data-stu-id="75fa2-142">For more information see [Unicode Data and Server Code Pages](../extended-stored-procedures-programming/unicode-data-and-server-code-pages.md).</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="75fa2-143">Необходимо тщательно просмотреть исходный код расширенных хранимых процедур и проверить скомпилированные библиотеки DLL перед их установкой на рабочий сервер.</span><span class="sxs-lookup"><span data-stu-id="75fa2-143">You should thoroughly review the source code of extended stored procedures, and you should test the compiled DLLs before you install them on a production server.</span></span> <span data-ttu-id="75fa2-144">Сведения о проверке безопасности см. на следующем [веб-сайте Майкрософт](https://go.microsoft.com/fwlink/?LinkID=54761&amp;clcid=0x409https://msdn.microsoft.com/security/).</span><span class="sxs-lookup"><span data-stu-id="75fa2-144">For information about security review and testing, see this [Microsoft Web site](https://go.microsoft.com/fwlink/?LinkID=54761&amp;clcid=0x409https://msdn.microsoft.com/security/).</span></span>  
  
  
