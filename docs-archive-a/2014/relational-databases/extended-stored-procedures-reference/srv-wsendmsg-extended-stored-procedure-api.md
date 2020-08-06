---
title: srv_wsendmsg (интерфейс API расширенных хранимых процедур) | Документы Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: stored-procedures
ms.topic: reference
api_name:
- srv_wsendmsg
api_location:
- opends60.dll
topic_type:
- apiref
dev_langs:
- C++
helpviewer_keywords:
- srv_wsendmsg
ms.assetid: f2153076-32c9-4a52-8e1b-fc9618153543
author: rothja
ms.author: jroth
ms.openlocfilehash: 4cc915cce0befccb5c5af58e703c11b750af855b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87751004"
---
# <a name="srv_wsendmsg-extended-stored-procedure-api"></a><span data-ttu-id="c44aa-102">srv_wsendmsg (API-интерфейс расширенных хранимых процедур)</span><span class="sxs-lookup"><span data-stu-id="c44aa-102">srv_wsendmsg (Extended Stored Procedure API)</span></span>
    
> [!IMPORTANT]  
>  [!INCLUDE[ssNoteDepFutureDontUse](../../includes/ssnotedepfuturedontuse-md.md)] <span data-ttu-id="c44aa-103">Используйте вместо этого интеграцию со средой CLR.</span><span class="sxs-lookup"><span data-stu-id="c44aa-103">Use CLR integration instead.</span></span>  
  
 <span data-ttu-id="c44aa-104">Отправляет клиенту сообщение в Юникоде.</span><span class="sxs-lookup"><span data-stu-id="c44aa-104">Sends a Unicode message to the client.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c44aa-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="c44aa-105">Syntax</span></span>  
  
```  
  
int srv_wsendmsg(SRV_PROC *   
srvproc  
, int   
msgnum  
, int   
severity  
, WCHAR *   
message  
, int   
msglen  
);  
  
```  
  
## <a name="arguments"></a><span data-ttu-id="c44aa-106">Аргументы</span><span class="sxs-lookup"><span data-stu-id="c44aa-106">Arguments</span></span>  
 <span data-ttu-id="c44aa-107">*srvproc*</span><span class="sxs-lookup"><span data-stu-id="c44aa-107">*srvproc*</span></span>  
 <span data-ttu-id="c44aa-108">Указатель на структуру SRV_PROC, который представляет собой дескриптор соединения с клиентом.</span><span class="sxs-lookup"><span data-stu-id="c44aa-108">Is a pointer to the SRV_PROC structure that is the handle for a particular client connection.</span></span> <span data-ttu-id="c44aa-109">Эта структура содержит сведения, которые используются библиотекой API-интерфейса расширенных хранимых процедур для управления связью и передачи данных между приложением и клиентом.</span><span class="sxs-lookup"><span data-stu-id="c44aa-109">The structure contains information the Extended Stored Procedure API library uses to manage communication and data between the application and the client.</span></span>  
  
 <span data-ttu-id="c44aa-110">*Номерсообщения*</span><span class="sxs-lookup"><span data-stu-id="c44aa-110">*Msgnum*</span></span>  
 <span data-ttu-id="c44aa-111">4-байтовый номер сообщения.</span><span class="sxs-lookup"><span data-stu-id="c44aa-111">Is a 4-byte message number.</span></span>  
  
 <span data-ttu-id="c44aa-112">*Уровень серьезности*</span><span class="sxs-lookup"><span data-stu-id="c44aa-112">*Severity*</span></span>  
 <span data-ttu-id="c44aa-113">Указывает серьезность ошибки.</span><span class="sxs-lookup"><span data-stu-id="c44aa-113">Specifies the severity of the error.</span></span> <span data-ttu-id="c44aa-114">Серьезность, меньше или равная 10, считается информационным сообщением, в противном случае — ошибкой.</span><span class="sxs-lookup"><span data-stu-id="c44aa-114">A severity less than or equal to 10 is considered an informational message; otherwise, it is an error.</span></span>  
  
 <span data-ttu-id="c44aa-115">*message*</span><span class="sxs-lookup"><span data-stu-id="c44aa-115">*message*</span></span>  
 <span data-ttu-id="c44aa-116">Является указателем на строку в Юникоде, которая должна быть отправлена клиенту.</span><span class="sxs-lookup"><span data-stu-id="c44aa-116">Is a pointer to a Unicode string to be sent to the client.</span></span>  
  
 <span data-ttu-id="c44aa-117">*msglen*</span><span class="sxs-lookup"><span data-stu-id="c44aa-117">*msglen*</span></span>  
 <span data-ttu-id="c44aa-118">Указывает длину *message*в символах.</span><span class="sxs-lookup"><span data-stu-id="c44aa-118">Specifies the length, in characters, of *message*.</span></span>  
  
## <a name="returns"></a><span data-ttu-id="c44aa-119">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="c44aa-119">Returns</span></span>  
 <span data-ttu-id="c44aa-120">SUCCEED или FAIL.</span><span class="sxs-lookup"><span data-stu-id="c44aa-120">SUCCEED or FAIL.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c44aa-121">Remarks</span><span class="sxs-lookup"><span data-stu-id="c44aa-121">Remarks</span></span>  
 <span data-ttu-id="c44aa-122">Эта функция используется для отправки сообщения в Юникоде.</span><span class="sxs-lookup"><span data-stu-id="c44aa-122">Use this function to send messages in Unicode.</span></span> <span data-ttu-id="c44aa-123">Она сходна с функцией **srv_sendmsg**, но сообщение, которое она отправляет, является строкой типа WCHAR, а не строкой типа DBCHAR.</span><span class="sxs-lookup"><span data-stu-id="c44aa-123">It is similar to **srv_sendmsg**, but the message it sends is a WCHAR string rather than type DBCHAR string.</span></span> <span data-ttu-id="c44aa-124">Следует отметить, что длина сообщения считается в символах, а не в байтах, а также *msglen* никогда не будет равно SRV_NULLTERM.</span><span class="sxs-lookup"><span data-stu-id="c44aa-124">Note that message length is reported in characters rather than bytes, and *msglen* will never be equal to SRV_NULLTERM.</span></span>  
  
 <span data-ttu-id="c44aa-125">Функция возвращает значение FAIL, если:</span><span class="sxs-lookup"><span data-stu-id="c44aa-125">The function returns FAIL when</span></span>  
  
-   <span data-ttu-id="c44aa-126">значение *msglen* лежит вне диапазона 0-32242;</span><span class="sxs-lookup"><span data-stu-id="c44aa-126">The *msglen* given is not in the range of 0-32242.</span></span>  
  
-   <span data-ttu-id="c44aa-127">значение *msglen* равно 0, но значение указателя сообщения равно NULL;</span><span class="sxs-lookup"><span data-stu-id="c44aa-127">The *msglen* given is 0 but the message pointer is NULL.</span></span>  
  
-   <span data-ttu-id="c44aa-128">при отправке сообщения об ошибке через сеть возникает ошибка.</span><span class="sxs-lookup"><span data-stu-id="c44aa-128">There is error when sending the error message through network.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="c44aa-129">Необходимо тщательно просмотреть исходный код расширенных хранимых процедур и проверить скомпилированные библиотеки DLL перед их установкой на рабочий сервер.</span><span class="sxs-lookup"><span data-stu-id="c44aa-129">You should thoroughly review the source code of extended stored procedures, and you should test the compiled DLLs before you install them on a production server.</span></span> <span data-ttu-id="c44aa-130">Сведения о проверке безопасности см. на следующем [веб-сайте Майкрософт](https://go.microsoft.com/fwlink/?LinkID=54761&amp;clcid=0x409https://msdn.microsoft.com/security/).</span><span class="sxs-lookup"><span data-stu-id="c44aa-130">For information about security review and testing, see this [Microsoft Web site](https://go.microsoft.com/fwlink/?LinkID=54761&amp;clcid=0x409https://msdn.microsoft.com/security/).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c44aa-131">См. также:</span><span class="sxs-lookup"><span data-stu-id="c44aa-131">See Also</span></span>  
 [<span data-ttu-id="c44aa-132">srv_sendmsg (интерфейс API расширенных хранимых процедур)</span><span class="sxs-lookup"><span data-stu-id="c44aa-132">srv_sendmsg &#40;Extended Stored Procedure API&#41;</span></span>](srv-sendmsg-extended-stored-procedure-api.md)  
  
  
