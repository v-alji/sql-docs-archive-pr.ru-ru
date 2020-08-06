---
title: srv_sendrow (интерфейс API расширенных хранимых процедур) | Документы Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: stored-procedures
ms.topic: reference
api_name:
- srv_sendrow
api_location:
- opends60.dll
topic_type:
- apiref
dev_langs:
- C++
helpviewer_keywords:
- srv_sendrow
ms.assetid: a08f608a-10e6-4bff-9b48-0d02e8026cdb
author: rothja
ms.author: jroth
ms.openlocfilehash: df40348b8792a70f84719abfb42152fda9487e6b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87752131"
---
# <a name="srv_sendrow-extended-stored-procedure-api"></a><span data-ttu-id="33f6e-102">srv_sendrow (API-интерфейс расширенных хранимых процедур)</span><span class="sxs-lookup"><span data-stu-id="33f6e-102">srv_sendrow (Extended Stored Procedure API)</span></span>
    
> [!IMPORTANT]  
>  [!INCLUDE[ssNoteDepFutureDontUse](../../includes/ssnotedepfuturedontuse-md.md)] <span data-ttu-id="33f6e-103">Используйте вместо этого интеграцию со средой CLR.</span><span class="sxs-lookup"><span data-stu-id="33f6e-103">Use CLR integration instead.</span></span>  
  
 <span data-ttu-id="33f6e-104">Передает строку данных на клиент.</span><span class="sxs-lookup"><span data-stu-id="33f6e-104">Transmits a row of data to the client.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="33f6e-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="33f6e-105">Syntax</span></span>  
  
```  
  
int srv_sendrow ( SRV_PROC *  
srvproc   
);  
  
```  
  
## <a name="arguments"></a><span data-ttu-id="33f6e-106">Аргументы</span><span class="sxs-lookup"><span data-stu-id="33f6e-106">Arguments</span></span>  
 <span data-ttu-id="33f6e-107">*srvproc*</span><span class="sxs-lookup"><span data-stu-id="33f6e-107">*srvproc*</span></span>  
 <span data-ttu-id="33f6e-108">Указатель на структуру SRV_PROC, который представляет собой дескриптор соединения с клиентом (в данном случае — дескриптор, который получил запрос языка).</span><span class="sxs-lookup"><span data-stu-id="33f6e-108">Is a pointer to the SRV_PROC structure that is the handle for a particular client connection (in this case, the handle that received the language request).</span></span> <span data-ttu-id="33f6e-109">Структура содержит сведения, которые используются библиотекой API-интерфейса расширенных хранимых процедур для управления связью и передачи данных между приложением и клиентом.</span><span class="sxs-lookup"><span data-stu-id="33f6e-109">The structure contains information that the Extended Stored Procedure API library uses to manage communication and data between the application and the client.</span></span>  
  
## <a name="returns"></a><span data-ttu-id="33f6e-110">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="33f6e-110">Returns</span></span>  
 <span data-ttu-id="33f6e-111">SUCCEED или FAIL.</span><span class="sxs-lookup"><span data-stu-id="33f6e-111">SUCCEED or FAIL.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="33f6e-112">Remarks</span><span class="sxs-lookup"><span data-stu-id="33f6e-112">Remarks</span></span>  
 <span data-ttu-id="33f6e-113">Функция **srv_sendrow** вызывается по разу для каждой из строк, отправляемых клиенту.</span><span class="sxs-lookup"><span data-stu-id="33f6e-113">The **srv_sendrow** function is called once for each row sent to the client.</span></span> <span data-ttu-id="33f6e-114">Все строки должны быть отправлены клиенту до того, как будут отправлены любые сообщения, значения состояния или состояние завершения с помощью функций **srv_sendmsg**, **srv_status**или **srv_senddone**.</span><span class="sxs-lookup"><span data-stu-id="33f6e-114">All rows must be sent to the client before any messages, status values, or completion statuses are sent with **srv_sendmsg**, **srv_status**, or **srv_senddone**.</span></span>  
  
 <span data-ttu-id="33f6e-115">При отправке строки, для которой не все столбцы определены с помощью функции **srv_describe** , API-интерфейс расширенных хранимых процедур выдаст информационное сообщение об ошибке и вернет клиенту значение FAIL.</span><span class="sxs-lookup"><span data-stu-id="33f6e-115">Sending a row that has not had all its columns defined with **srv_describe** causes the Extended Stored Procedure API application to raise an informational error message and return FAIL to the client.</span></span> <span data-ttu-id="33f6e-116">В этом случае строка не отправляется.</span><span class="sxs-lookup"><span data-stu-id="33f6e-116">In this case, the row is not sent.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="33f6e-117">API-интерфейс расширенных хранимых процедур не поддерживает отправку клиенту вычисляемых строк.</span><span class="sxs-lookup"><span data-stu-id="33f6e-117">The Extended Stored Procedure API does not support sending compute rows to the client.</span></span> <span data-ttu-id="33f6e-118">Кроме того, если клиенту отправляется строка данных, содержащая `ntext`, `text` или `image`, то в нее не включаются текстовый указатель и текстовая отметка времени.</span><span class="sxs-lookup"><span data-stu-id="33f6e-118">Also, if a row containing `ntext`, `text`, or `image` data is sent to the client, the text pointer and text timestamp are not included.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="33f6e-119">Необходимо тщательно просмотреть исходный код расширенных хранимых процедур и проверить скомпилированные библиотеки DLL перед их установкой на рабочий сервер.</span><span class="sxs-lookup"><span data-stu-id="33f6e-119">You should thoroughly review the source code of extended stored procedures, and you should test the compiled DLLs before you install them on a production server.</span></span> <span data-ttu-id="33f6e-120">Сведения о проверке безопасности см. на следующем [веб-сайте Майкрософт](https://go.microsoft.com/fwlink/?LinkID=54761&amp;clcid=0x409https://msdn.microsoft.com/security/).</span><span class="sxs-lookup"><span data-stu-id="33f6e-120">For information about security review and testing, see this [Microsoft Web site](https://go.microsoft.com/fwlink/?LinkID=54761&amp;clcid=0x409https://msdn.microsoft.com/security/).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="33f6e-121">См. также:</span><span class="sxs-lookup"><span data-stu-id="33f6e-121">See Also</span></span>  
 [<span data-ttu-id="33f6e-122">srv_describe (интерфейс API расширенных хранимых процедур)</span><span class="sxs-lookup"><span data-stu-id="33f6e-122">srv_describe &#40;Extended Stored Procedure API&#41;</span></span>](srv-describe-extended-stored-procedure-api.md)  
  
  
