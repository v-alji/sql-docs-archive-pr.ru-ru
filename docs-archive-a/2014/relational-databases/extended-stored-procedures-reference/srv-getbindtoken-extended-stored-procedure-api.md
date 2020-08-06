---
title: srv_getbindtoken (интерфейс API расширенных хранимых процедур) | Документы Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: stored-procedures
ms.topic: reference
api_name:
- srv_getbindtoken
api_location:
- opends60.dll
topic_type:
- apiref
dev_langs:
- C++
helpviewer_keywords:
- srv_getbindtoken
ms.assetid: c947d011-08ac-4fb8-b925-3da6e0999277
author: rothja
ms.author: jroth
ms.openlocfilehash: d42f95c8a7df87f20ebaa30501b96b5f2a00815a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87668328"
---
# <a name="srv_getbindtoken-extended-stored-procedure-api"></a><span data-ttu-id="06dea-102">srv_getbindtoken (API-интерфейс расширенных хранимых процедур)</span><span class="sxs-lookup"><span data-stu-id="06dea-102">srv_getbindtoken (Extended Stored Procedure API)</span></span>
    
> [!IMPORTANT]  
>  [!INCLUDE[ssNoteDepFutureDontUse](../../includes/ssnotedepfuturedontuse-md.md)] <span data-ttu-id="06dea-103">Используйте вместо этого интеграцию со средой CLR.</span><span class="sxs-lookup"><span data-stu-id="06dea-103">Use CLR integration instead.</span></span>  
  
 <span data-ttu-id="06dea-104">Получает токен привязки транзакции в текущем сеансе клиента, который вызывает расширенную хранимую процедуру.</span><span class="sxs-lookup"><span data-stu-id="06dea-104">Obtains a bind token of the transaction in the current client session that invokes the extended stored procedure.</span></span>  
  
 <span data-ttu-id="06dea-105">После этого расширенная хранимая процедура может использовать **sp_bindsession** для привязки любого созданного ею на том же сервере сеанса к существующей транзакции, чтобы новый сеанс мог совместно использовать одно пространство блокировки транзакций с клиентским сеансом, вызвавшим расширенную хранимую процедуру.</span><span class="sxs-lookup"><span data-stu-id="06dea-105">The extended stored procedure can then use **sp_bindsession** to bind any new session it creates against the same server to the existing transaction so that the new session can share the same transaction lock space with the client session that invoked the extended stored procedure.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="06dea-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="06dea-106">Syntax</span></span>  
  
```  
  
int srv_getbindtoken (  
SRV_PROC*  
srvproc  
,  
char*  
bindtoken  
);  
  
```  
  
## <a name="arguments"></a><span data-ttu-id="06dea-107">Аргументы</span><span class="sxs-lookup"><span data-stu-id="06dea-107">Arguments</span></span>  
 <span data-ttu-id="06dea-108">*srvproc*</span><span class="sxs-lookup"><span data-stu-id="06dea-108">*srvproc*</span></span>  
 <span data-ttu-id="06dea-109">Указатель на структуру SRV_PROC, который представляет собой дескриптор соединения с клиентом.</span><span class="sxs-lookup"><span data-stu-id="06dea-109">Is a pointer to the SRV_PROC structure that is the handle for a particular client connection.</span></span> <span data-ttu-id="06dea-110">В этой структуре содержатся все сведения, которые библиотека API-интерфейса расширенных хранимых процедур использует для управления обменом данными между приложением и клиентом.</span><span class="sxs-lookup"><span data-stu-id="06dea-110">The structure contains all the information that the Extended Stored Procedure API library uses to manage communications and data between the application and the client.</span></span>  
  
 <span data-ttu-id="06dea-111">*bindtoken*</span><span class="sxs-lookup"><span data-stu-id="06dea-111">*bindtoken*</span></span>  
 <span data-ttu-id="06dea-112">Указатель на буфер, в который будет скопирован токен привязки.</span><span class="sxs-lookup"><span data-stu-id="06dea-112">Is a pointer to a buffer where the bind token will be copied.</span></span> <span data-ttu-id="06dea-113">Токен привязки представлен как строка, оканчивающаяся нулевым байтом.</span><span class="sxs-lookup"><span data-stu-id="06dea-113">The bind token is represented as a null-terminated string.</span></span> <span data-ttu-id="06dea-114">Указываемый буфер должен иметь длину не менее 255 байт.</span><span class="sxs-lookup"><span data-stu-id="06dea-114">The buffer you specify should be at least 255 bytes in length.</span></span>  
  
## <a name="returns"></a><span data-ttu-id="06dea-115">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="06dea-115">Returns</span></span>  
 <span data-ttu-id="06dea-116">SUCCEED или FAIL.</span><span class="sxs-lookup"><span data-stu-id="06dea-116">SUCCEED or FAIL.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="06dea-117">Remarks</span><span class="sxs-lookup"><span data-stu-id="06dea-117">Remarks</span></span>  
  
### <a name="to-bind-an-extended-stored-procedure-session-to-the-client-session-that-called-it-so-they-share-the-same-transaction-lock-space"></a><span data-ttu-id="06dea-118">Привязка сеанса расширенной хранимой процедуры к сеансу вызывающего ее клиента для совместного использования пространства блокировки транзакций</span><span class="sxs-lookup"><span data-stu-id="06dea-118">To bind an extended stored procedure session to the client session that called it so they share the same transaction lock space</span></span>  
  
1.  <span data-ttu-id="06dea-119">Расширенная хранимая процедура вызывает функцию **svr_getbindtoken**, чтобы получить токен привязки для текущей транзакции в сеансе.</span><span class="sxs-lookup"><span data-stu-id="06dea-119">The extended stored procedure calls **svr_getbindtoken** to get the bind token for the current transaction in the session.</span></span> <span data-ttu-id="06dea-120">Токен возвращается в параметре *bindtoken*.</span><span class="sxs-lookup"><span data-stu-id="06dea-120">The token is returned in the given *bindtoken* parameter.</span></span>  
  
2.  <span data-ttu-id="06dea-121">Расширенная хранимая процедура открывает новый сеанс на том же сервере.</span><span class="sxs-lookup"><span data-stu-id="06dea-121">The extended stored procedure opens new session(s) against the same server.</span></span> <span data-ttu-id="06dea-122">В этом сеансе расширенная хранимая процедура использует токен привязки в хранимой процедуре **sp_bindsession** для привязки нового сеанса к той же транзакции.</span><span class="sxs-lookup"><span data-stu-id="06dea-122">Inside that session, the extended stored procedure uses the bind token with **sp_bindsession** to bind the new session to the same transaction.</span></span> <span data-ttu-id="06dea-123">Расширенная хранимая процедура может создать несколько сеансов и привязать их к одной транзакции.</span><span class="sxs-lookup"><span data-stu-id="06dea-123">The extended stored procedure can create multiple sessions and bind all the sessions to the same transaction.</span></span>  
  
3.  <span data-ttu-id="06dea-124">Связанный сеанс освобождается при возврате из расширенной хранимой процедуры или когда **sp_bindsession** вызывается с пустой строкой.</span><span class="sxs-lookup"><span data-stu-id="06dea-124">A bound session is unbound when the external stored procedure returns or when **sp_bindsession** is called with an empty string.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="06dea-125">Только один связанный сеанс может получить доступ к общему соединению в один момент времени.</span><span class="sxs-lookup"><span data-stu-id="06dea-125">Only one bound session at a time can have access to a shared connection.</span></span> <span data-ttu-id="06dea-126">Если один сеанс в настоящий момент выполняет инструкцию на сервере или ожидает результаты с сервера, то никакой другой сеанс, совместно использующий это связанное соединение, не может получить доступ к серверу, пока текущий сеанс не завершит выполнение инструкции.</span><span class="sxs-lookup"><span data-stu-id="06dea-126">If one session is currently executing a statement at the server or has results pending from the server, no other sessions sharing the same bound connection can gain access to the server until the current session has finished executing the current statement.</span></span> <span data-ttu-id="06dea-127">Если сеанс пытается получить доступ к соединению, пока сервер занят, то для этого сеанса возвращается ошибка, указывающая, что соединение используется, и конфликтующему сеансу следует повторить попытку позже.</span><span class="sxs-lookup"><span data-stu-id="06dea-127">If a session attempts to gain access to the connection while the server is busy, an error is returned to the conflicting session indicating the connection is in use and the session should retry later.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="06dea-128">Необходимо тщательно просмотреть исходный код расширенных хранимых процедур и проверить скомпилированные библиотеки DLL перед их установкой на рабочий сервер.</span><span class="sxs-lookup"><span data-stu-id="06dea-128">You should thoroughly review the source code of extended stored procedures, and you should test the compiled DLLs before you install them on a production server.</span></span> <span data-ttu-id="06dea-129">Сведения о проверке безопасности см. на следующем [веб-сайте Майкрософт](https://go.microsoft.com/fwlink/?LinkID=54761&amp;clcid=0x409https://msdn.microsoft.com/security/).</span><span class="sxs-lookup"><span data-stu-id="06dea-129">For information about security review and testing, see this [Microsoft Web site](https://go.microsoft.com/fwlink/?LinkID=54761&amp;clcid=0x409https://msdn.microsoft.com/security/).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="06dea-130">См. также:</span><span class="sxs-lookup"><span data-stu-id="06dea-130">See Also</span></span>  
 <span data-ttu-id="06dea-131">[sp_bindsession (Transact-SQL)](/sql/relational-databases/system-stored-procedures/sp-bindsession-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="06dea-131">[sp_bindsession &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-bindsession-transact-sql) </span></span>  
 [<span data-ttu-id="06dea-132">sp_getbindtoken (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="06dea-132">sp_getbindtoken &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-getbindtoken-transact-sql)  
  
  
