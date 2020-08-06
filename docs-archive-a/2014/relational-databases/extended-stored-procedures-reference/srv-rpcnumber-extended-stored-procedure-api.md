---
title: srv_rpcnumber (интерфейс API расширенных хранимых процедур) | Документы Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: stored-procedures
ms.topic: reference
api_name:
- srv_rpcnumber
api_location:
- opends60.dll
topic_type:
- apiref
dev_langs:
- C++
helpviewer_keywords:
- srv_rpcnumber
ms.assetid: 3094085e-fe9e-423d-bf87-7852352c2d26
author: rothja
ms.author: jroth
ms.openlocfilehash: 25f30f8288125cf64d6b10a867d6af03c0f8ee91
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87751012"
---
# <a name="srv_rpcnumber-extended-stored-procedure-api"></a><span data-ttu-id="921e1-102">srv_rpcnumber (API-интерфейс расширенных хранимых процедур)</span><span class="sxs-lookup"><span data-stu-id="921e1-102">srv_rpcnumber (Extended Stored Procedure API)</span></span>
    
> [!IMPORTANT]  
>  [!INCLUDE[ssNoteDepFutureDontUse](../../includes/ssnotedepfuturedontuse-md.md)] <span data-ttu-id="921e1-103">Используйте вместо этого интеграцию со средой CLR.</span><span class="sxs-lookup"><span data-stu-id="921e1-103">Use CLR integration instead.</span></span>  
  
 <span data-ttu-id="921e1-104">Возвращает компонент номера для текущей удаленной хранимой процедуры.</span><span class="sxs-lookup"><span data-stu-id="921e1-104">Returns the number component for the current remote stored procedure call.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="921e1-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="921e1-105">Syntax</span></span>  
  
```  
  
int srv_rpcnumber ( SRV_PROC *  
srvproc   
)  
  
```  
  
## <a name="arguments"></a><span data-ttu-id="921e1-106">Аргументы</span><span class="sxs-lookup"><span data-stu-id="921e1-106">Arguments</span></span>  
 <span data-ttu-id="921e1-107">*srvproc*</span><span class="sxs-lookup"><span data-stu-id="921e1-107">*srvproc*</span></span>  
 <span data-ttu-id="921e1-108">Указатель на структуру SRV_PROC, представляющую собой дескриптор соединения с клиентом (в данном случае — дескриптор, получивший удаленную хранимую процедуру).</span><span class="sxs-lookup"><span data-stu-id="921e1-108">Is a pointer to the SRV_PROC structure that is the handle for a particular client connection (in this case, the handle that received the remote stored procedure).</span></span> <span data-ttu-id="921e1-109">Структура содержит сведения, которые используются библиотекой API-интерфейса расширенных хранимых процедур для управления связью и передачи данных между приложением и клиентом.</span><span class="sxs-lookup"><span data-stu-id="921e1-109">The structure contains information that the Extended Stored Procedure API library uses to manage communication and data between the application and the client.</span></span>  
  
## <a name="returns"></a><span data-ttu-id="921e1-110">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="921e1-110">Returns</span></span>  
 <span data-ttu-id="921e1-111">Компонент номера для текущей удаленной хранимой процедуры.</span><span class="sxs-lookup"><span data-stu-id="921e1-111">The number component for the current remote stored procedure.</span></span> <span data-ttu-id="921e1-112">Если клиент при выполнении удаленной хранимой процедуры не использует компонент номера (либо при отсутствии текущей удаленной хранимой процедуры), возвращается значение -1.</span><span class="sxs-lookup"><span data-stu-id="921e1-112">If the client does not use a number component when running the remote stored procedure or if there is no current remote stored procedure, it returns - 1.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="921e1-113">Remarks</span><span class="sxs-lookup"><span data-stu-id="921e1-113">Remarks</span></span>  
 <span data-ttu-id="921e1-114">Эта функция возвращает только компонент номера удаленной хранимой процедуры.</span><span class="sxs-lookup"><span data-stu-id="921e1-114">This function returns only the number component of the remote stored procedure.</span></span> <span data-ttu-id="921e1-115">Она не включает необязательные описатели для владельца, имени удаленной хранимой процедуры и имени базы данных.</span><span class="sxs-lookup"><span data-stu-id="921e1-115">It does not include the optional specifiers for owner, remote stored procedure name, and database name.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="921e1-116">Необходимо тщательно просмотреть исходный код расширенных хранимых процедур и проверить скомпилированные библиотеки DLL перед их установкой на рабочий сервер.</span><span class="sxs-lookup"><span data-stu-id="921e1-116">You should thoroughly review the source code of extended stored procedures, and you should test the compiled DLLs before you install them on a production server.</span></span> <span data-ttu-id="921e1-117">Сведения о проверке безопасности см. на следующем [веб-сайте Майкрософт](https://go.microsoft.com/fwlink/?LinkID=54761&amp;clcid=0x409https://msdn.microsoft.com/security/).</span><span class="sxs-lookup"><span data-stu-id="921e1-117">For information about security review and testing, see this [Microsoft Web site](https://go.microsoft.com/fwlink/?LinkID=54761&amp;clcid=0x409https://msdn.microsoft.com/security/).</span></span>  
  
  
