---
title: srv_message_handler (интерфейс API расширенных хранимых процедур) | Документы Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: stored-procedures
ms.topic: reference
api_name:
- srv_message_handler
api_location:
- opends60.dll
topic_type:
- apiref
dev_langs:
- C++
helpviewer_keywords:
- srv_message_handler
ms.assetid: 41bcd057-436f-4fa8-8293-fc8057a30877
author: rothja
ms.author: jroth
ms.openlocfilehash: 7e7b6472ed4fabb6dc2d545eb51a1e026635ce19
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87657109"
---
# <a name="srv_message_handler-extended-stored-procedure-api"></a><span data-ttu-id="7bad1-102">srv_message_handler (API-интерфейс расширенных хранимых процедур)</span><span class="sxs-lookup"><span data-stu-id="7bad1-102">srv_message_handler (Extended Stored Procedure API)</span></span>
    
> [!IMPORTANT]  
>  [!INCLUDE[ssNoteDepFutureDontUse](../../includes/ssnotedepfuturedontuse-md.md)] <span data-ttu-id="7bad1-103">Используйте вместо этого интеграцию со средой CLR.</span><span class="sxs-lookup"><span data-stu-id="7bad1-103">Use CLR integration instead.</span></span>  
  
 <span data-ttu-id="7bad1-104">Вызывает установленный обработчик сообщений API-интерфейса расширенных хранимых процедур.</span><span class="sxs-lookup"><span data-stu-id="7bad1-104">Calls the installed Extended Stored Procedure API message handler.</span></span> <span data-ttu-id="7bad1-105">Эта функция обычно используется для вызова [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] из расширенной хранимой процедуры, чтобы зарегистрировать ошибку (определенную расширенной хранимой процедурой) в [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] файле журнала ошибок или [!INCLUDE[msCoName](../../includes/msconame-md.md)] журнале приложений Windows.</span><span class="sxs-lookup"><span data-stu-id="7bad1-105">This function is usually used to call [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] from an extended stored procedure to log an error (defined by the extended stored procedure) in the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] error log file or the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows application log.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7bad1-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="7bad1-106">Syntax</span></span>  
  
```  
  
int srv_message_handler (  
SRV_PROC *  
srvproc  
,  
int  
errornum  
,  
BYTE   
severity  
,  
BYTE  
state  
,  
int  
oserrnum  
,  
char *  
errtext  
,  
int  
errtextlen  
,  
char *  
oserrtext  
,  
int  
oserrtextlen  
);  
  
```  
  
## <a name="arguments"></a><span data-ttu-id="7bad1-107">Аргументы</span><span class="sxs-lookup"><span data-stu-id="7bad1-107">Arguments</span></span>  
 <span data-ttu-id="7bad1-108">*srvproc*</span><span class="sxs-lookup"><span data-stu-id="7bad1-108">*srvproc*</span></span>  
 <span data-ttu-id="7bad1-109">Указатель на структуру SRV_PROC, который представляет собой дескриптор соединения с клиентом.</span><span class="sxs-lookup"><span data-stu-id="7bad1-109">Is a pointer to the SRV_PROC structure that is the handle for a particular client connection.</span></span> <span data-ttu-id="7bad1-110">Параметр *srvproc* содержит сведения, которые используются для управления связью и передачей данных между приложением и клиентом.</span><span class="sxs-lookup"><span data-stu-id="7bad1-110">The *srvproc* parameter contains information that is used to manage communication and data between the application and the client.</span></span>  
  
 <span data-ttu-id="7bad1-111">*errornum*</span><span class="sxs-lookup"><span data-stu-id="7bad1-111">*errornum*</span></span>  
 <span data-ttu-id="7bad1-112">Номер ошибки, определенный расширенной хранимой процедурой.</span><span class="sxs-lookup"><span data-stu-id="7bad1-112">Is an error number defined by the extended stored procedure.</span></span> <span data-ttu-id="7bad1-113">Это значение должно быть от 50 001 до 2 147 483 647.</span><span class="sxs-lookup"><span data-stu-id="7bad1-113">This number must be from 50,001 through 2,147,483,647.</span></span>  
  
 <span data-ttu-id="7bad1-114">*severity*</span><span class="sxs-lookup"><span data-stu-id="7bad1-114">*severity*</span></span>  
 <span data-ttu-id="7bad1-115">Стандартное значение серьезности [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] для ошибки.</span><span class="sxs-lookup"><span data-stu-id="7bad1-115">Is a standard [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] severity value for the error.</span></span> <span data-ttu-id="7bad1-116">Это значение должно быть от 0 до 24.</span><span class="sxs-lookup"><span data-stu-id="7bad1-116">This number must be from 0 through 24.</span></span>  
  
 <span data-ttu-id="7bad1-117">*state*</span><span class="sxs-lookup"><span data-stu-id="7bad1-117">*state*</span></span>  
 <span data-ttu-id="7bad1-118">Значение состояния [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] для ошибки.</span><span class="sxs-lookup"><span data-stu-id="7bad1-118">Is a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] state value for the error.</span></span>  
  
 <span data-ttu-id="7bad1-119">*oserrnum*</span><span class="sxs-lookup"><span data-stu-id="7bad1-119">*oserrnum*</span></span>  
 <span data-ttu-id="7bad1-120">Номер ошибки операционной системы.</span><span class="sxs-lookup"><span data-stu-id="7bad1-120">Is the operating-system error number.</span></span> <span data-ttu-id="7bad1-121">Этот аргумент игнорируется.</span><span class="sxs-lookup"><span data-stu-id="7bad1-121">This argument is ignored.</span></span>  
  
 <span data-ttu-id="7bad1-122">*errtext*</span><span class="sxs-lookup"><span data-stu-id="7bad1-122">*errtext*</span></span>  
 <span data-ttu-id="7bad1-123">Описание ошибки *errornum* расширенной хранимой процедуры.</span><span class="sxs-lookup"><span data-stu-id="7bad1-123">Is the description of the extended stored procedure error *errornum*.</span></span>  
  
 <span data-ttu-id="7bad1-124">*errtextlen*</span><span class="sxs-lookup"><span data-stu-id="7bad1-124">*errtextlen*</span></span>  
 <span data-ttu-id="7bad1-125">Длина строки ошибки *errtext* расширенной хранимой процедуры.</span><span class="sxs-lookup"><span data-stu-id="7bad1-125">Is the length of the extended stored procedure error string *errtext*.</span></span>  
  
 <span data-ttu-id="7bad1-126">*oserrtext*</span><span class="sxs-lookup"><span data-stu-id="7bad1-126">*oserrtext*</span></span>  
 <span data-ttu-id="7bad1-127">Описание ошибки операционной системы *oserrnum*.</span><span class="sxs-lookup"><span data-stu-id="7bad1-127">Is the description of the operating-system error *oserrnum*.</span></span> <span data-ttu-id="7bad1-128">Этот аргумент игнорируется.</span><span class="sxs-lookup"><span data-stu-id="7bad1-128">This argument is ignored.</span></span>  
  
 <span data-ttu-id="7bad1-129">*oserrtextlen*</span><span class="sxs-lookup"><span data-stu-id="7bad1-129">*oserrtextlen*</span></span>  
 <span data-ttu-id="7bad1-130">Длина строки ошибки операционной системы *oserrtext*.</span><span class="sxs-lookup"><span data-stu-id="7bad1-130">Is the length of the operating-system error string *oserrtext*.</span></span>  
  
## <a name="returns"></a><span data-ttu-id="7bad1-131">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="7bad1-131">Returns</span></span>  
 <span data-ttu-id="7bad1-132">SUCCEED или FAIL.</span><span class="sxs-lookup"><span data-stu-id="7bad1-132">SUCCEED or FAIL.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="7bad1-133">Remarks</span><span class="sxs-lookup"><span data-stu-id="7bad1-133">Remarks</span></span>  
 <span data-ttu-id="7bad1-134">Функция **srv_message_handler** обеспечивает интеграцию расширенной хранимой процедуры с централизованными функциями регистрации ошибок и подготовки отчетов [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="7bad1-134">The **srv_message_handler** function enables an extended stored procedure to integrate with the centralized error logging and reporting features of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="7bad1-135">Можно назначить предупреждения [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] для событий из расширенных хранимых процедур, и агент SQL Server будет отслеживать состояние этих предупреждений.</span><span class="sxs-lookup"><span data-stu-id="7bad1-135">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] alerts can be established for events from extended stored procedures, and SQL Server Agent will monitor for these alert conditions.</span></span>  
  
 <span data-ttu-id="7bad1-136">Если сообщение об ошибке длиннее, оно усекается до 412 байт.</span><span class="sxs-lookup"><span data-stu-id="7bad1-136">If the error message is longer, it is truncated to 412 bytes.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="7bad1-137">Необходимо тщательно просмотреть исходный код расширенных хранимых процедур и проверить скомпилированные библиотеки DLL перед их установкой на рабочий сервер.</span><span class="sxs-lookup"><span data-stu-id="7bad1-137">You should thoroughly review the source code of extended stored procedures, and you should test the compiled DLLs before you install them on a production server.</span></span> <span data-ttu-id="7bad1-138">Сведения о проверке безопасности см. на следующем [веб-сайте Майкрософт](https://go.microsoft.com/fwlink/?LinkID=54761&amp;clcid=0x409https://msdn.microsoft.com/security/).</span><span class="sxs-lookup"><span data-stu-id="7bad1-138">For information about security review and testing, see this [Microsoft Web site](https://go.microsoft.com/fwlink/?LinkID=54761&amp;clcid=0x409https://msdn.microsoft.com/security/).</span></span>  
  
  
