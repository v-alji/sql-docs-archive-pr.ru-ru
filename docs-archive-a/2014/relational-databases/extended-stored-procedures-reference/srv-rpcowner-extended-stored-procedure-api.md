---
title: srv_rpcowner (интерфейс API расширенных хранимых процедур) | Документы Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: stored-procedures
ms.topic: reference
api_name:
- srv_rpcowner
api_location:
- opends60.dll
topic_type:
- apiref
dev_langs:
- C++
helpviewer_keywords:
- srv_rpcowner
ms.assetid: e81a60e6-14ea-47bc-a11c-3d7635344447
author: rothja
ms.author: jroth
ms.openlocfilehash: f903870d0ee01256addb1557eb7e9123853b39e6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87752144"
---
# <a name="srv_rpcowner-extended-stored-procedure-api"></a><span data-ttu-id="2f25f-102">srv_rpcowner (API-интерфейс расширенных хранимых процедур)</span><span class="sxs-lookup"><span data-stu-id="2f25f-102">srv_rpcowner (Extended Stored Procedure API)</span></span>
    
> [!IMPORTANT]  
>  [!INCLUDE[ssNoteDepFutureDontUse](../../includes/ssnotedepfuturedontuse-md.md)] <span data-ttu-id="2f25f-103">Используйте вместо этого интеграцию со средой CLR.</span><span class="sxs-lookup"><span data-stu-id="2f25f-103">Use CLR integration instead.</span></span>  
  
 <span data-ttu-id="2f25f-104">Возвращает компонент владельца для текущей удаленной хранимой процедуры.</span><span class="sxs-lookup"><span data-stu-id="2f25f-104">Returns the owner component for the current remote stored procedure.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2f25f-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="2f25f-105">Syntax</span></span>  
  
```  
  
DBCHAR * srv_rpcowner (  
SRV_PROC *  
srvproc  
,  
int *  
len   
);  
  
```  
  
## <a name="arguments"></a><span data-ttu-id="2f25f-106">Аргументы</span><span class="sxs-lookup"><span data-stu-id="2f25f-106">Arguments</span></span>  
 <span data-ttu-id="2f25f-107">*srvproc*</span><span class="sxs-lookup"><span data-stu-id="2f25f-107">*srvproc*</span></span>  
 <span data-ttu-id="2f25f-108">Указатель на структуру SRV_PROC, представляющую собой дескриптор соединения с клиентом (в данном случае — дескриптор, получивший удаленную хранимую процедуру).</span><span class="sxs-lookup"><span data-stu-id="2f25f-108">Is a pointer to the SRV_PROC structure that is the handle for a particular client connection (in this case, the handle that received the remote stored procedure).</span></span> <span data-ttu-id="2f25f-109">Структура содержит сведения, которые используются библиотекой API-интерфейса расширенных хранимых процедур для управления связью и передачи данных между приложением и клиентом.</span><span class="sxs-lookup"><span data-stu-id="2f25f-109">The structure contains information that the Extended Stored Procedure API library uses to manage communication and data between the application and the client.</span></span>  
  
 <span data-ttu-id="2f25f-110">*len*</span><span class="sxs-lookup"><span data-stu-id="2f25f-110">*len*</span></span>  
 <span data-ttu-id="2f25f-111">Указатель на целочисленную переменную, получающую значение длины имени владельца.</span><span class="sxs-lookup"><span data-stu-id="2f25f-111">Is a pointer to an integer variable that receives the length of the owner name.</span></span> <span data-ttu-id="2f25f-112">Параметр *len* может быть пустым; в этом случае длина компонента владельца не возвращается.</span><span class="sxs-lookup"><span data-stu-id="2f25f-112">The parameter *len* can be NULL, in which case the length of the owner component is not returned.</span></span>  
  
## <a name="returns"></a><span data-ttu-id="2f25f-113">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="2f25f-113">Returns</span></span>  
 <span data-ttu-id="2f25f-114">Указатель DBCHAR на оканчивающийся нулевым байтом компонент владельца для текущей удаленной хранимой процедуры.</span><span class="sxs-lookup"><span data-stu-id="2f25f-114">A DBCHAR pointer to the null-terminated owner component for the current remote stored procedure.</span></span> <span data-ttu-id="2f25f-115">Если текущей удаленной хранимой процедуры нет, возвращается значение NULL, а переменная *len* принимает значение –1.</span><span class="sxs-lookup"><span data-stu-id="2f25f-115">If there is no current remote stored procedure, NULL is returned and *len* is set to - 1.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="2f25f-116">Remarks</span><span class="sxs-lookup"><span data-stu-id="2f25f-116">Remarks</span></span>  
 <span data-ttu-id="2f25f-117">Эта функция возвращает только компонент владельца удаленной хранимой процедуры.</span><span class="sxs-lookup"><span data-stu-id="2f25f-117">This function returns only the owner component of the remote stored procedure.</span></span> <span data-ttu-id="2f25f-118">В него не входят необязательные описатели для имени, имени удаленной хранимой процедуры и номера удаленной хранимой процедуры.</span><span class="sxs-lookup"><span data-stu-id="2f25f-118">It does not include the optional specifiers for name, remote stored procedure name, and remote stored procedure number.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="2f25f-119">Необходимо тщательно просмотреть исходный код расширенных хранимых процедур и проверить скомпилированные библиотеки DLL перед их установкой на рабочий сервер.</span><span class="sxs-lookup"><span data-stu-id="2f25f-119">You should thoroughly review the source code of extended stored procedures, and you should test the compiled DLLs before you install them on a production server.</span></span> <span data-ttu-id="2f25f-120">Сведения о проверке безопасности см. на следующем [веб-сайте Майкрософт](https://go.microsoft.com/fwlink/?LinkID=54761&amp;clcid=0x409https://msdn.microsoft.com/security/).</span><span class="sxs-lookup"><span data-stu-id="2f25f-120">For information about security review and testing, see this [Microsoft Web site](https://go.microsoft.com/fwlink/?LinkID=54761&amp;clcid=0x409https://msdn.microsoft.com/security/).</span></span>  
  
  
