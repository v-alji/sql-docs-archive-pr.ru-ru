---
title: srv_setutype (интерфейс API расширенных хранимых процедур) | Документы Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: stored-procedures
ms.topic: reference
api_name:
- srv_setutype
api_location:
- opends60.dll
topic_type:
- apiref
dev_langs:
- C++
helpviewer_keywords:
- srv_setutype
ms.assetid: 6160f15d-1b68-411e-ab6d-491ec288f264
author: rothja
ms.author: jroth
ms.openlocfilehash: e9e02605995e44f5869633d5e8778a955236005f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87739983"
---
# <a name="srv_setutype-extended-stored-procedure-api"></a><span data-ttu-id="1b834-102">srv_setutype (API-интерфейс расширенных хранимых процедур)</span><span class="sxs-lookup"><span data-stu-id="1b834-102">srv_setutype (Extended Stored Procedure API)</span></span>
    
> [!IMPORTANT]  
>  [!INCLUDE[ssNoteDepFutureDontUse](../../includes/ssnotedepfuturedontuse-md.md)] <span data-ttu-id="1b834-103">Используйте вместо этого интеграцию со средой CLR.</span><span class="sxs-lookup"><span data-stu-id="1b834-103">Use CLR integration instead.</span></span>  
  
 <span data-ttu-id="1b834-104">Устанавливает определяемый пользователем тип данных для столбца строки.</span><span class="sxs-lookup"><span data-stu-id="1b834-104">Sets the user-defined data type for a column in a row.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1b834-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="1b834-105">Syntax</span></span>  
  
```  
  
int srv_setutype (  
SRV_PROC *  
srvproc  
,  
int   
column  
,   
DBINT  
user_type   
);  
  
```  
  
## <a name="arguments"></a><span data-ttu-id="1b834-106">Аргументы</span><span class="sxs-lookup"><span data-stu-id="1b834-106">Arguments</span></span>  
 <span data-ttu-id="1b834-107">*srvproc*</span><span class="sxs-lookup"><span data-stu-id="1b834-107">*srvproc*</span></span>  
 <span data-ttu-id="1b834-108">Указатель на структуру SRV_PROC, который представляет собой дескриптор соединения с клиентом.</span><span class="sxs-lookup"><span data-stu-id="1b834-108">Is a pointer to the SRV_PROC structure that is the handle for a particular client connection.</span></span> <span data-ttu-id="1b834-109">Эта структура содержит сведения, которые используются библиотекой API-интерфейса расширенных хранимых процедур для управления связью и передачи данных между приложением и клиентом.</span><span class="sxs-lookup"><span data-stu-id="1b834-109">The structure contains information the Extended Stored Procedure API library uses to manage communication and data between the application and the client.</span></span>  
  
 <span data-ttu-id="1b834-110">*column*</span><span class="sxs-lookup"><span data-stu-id="1b834-110">*column*</span></span>  
 <span data-ttu-id="1b834-111">Указывает, какой столбец устанавливать.</span><span class="sxs-lookup"><span data-stu-id="1b834-111">Indicates which column to set.</span></span> <span data-ttu-id="1b834-112">Нумерация столбцов начинается с 1.</span><span class="sxs-lookup"><span data-stu-id="1b834-112">Columns are numbered beginning with 1.</span></span>  
  
 <span data-ttu-id="1b834-113">*user_type*</span><span class="sxs-lookup"><span data-stu-id="1b834-113">*user_type*</span></span>  
 <span data-ttu-id="1b834-114">Указывает код определяемого пользователем типа данных.</span><span class="sxs-lookup"><span data-stu-id="1b834-114">Specifies the user-defined data type code.</span></span>  
  
## <a name="returns"></a><span data-ttu-id="1b834-115">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="1b834-115">Returns</span></span>  
 <span data-ttu-id="1b834-116">SUCCEED или FAIL.</span><span class="sxs-lookup"><span data-stu-id="1b834-116">SUCCEED or FAIL.</span></span> <span data-ttu-id="1b834-117">Если столбец не существует, возвращает значение FAIL.</span><span class="sxs-lookup"><span data-stu-id="1b834-117">Returns FAIL if the column does not exist.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="1b834-118">Remarks</span><span class="sxs-lookup"><span data-stu-id="1b834-118">Remarks</span></span>  
 <span data-ttu-id="1b834-119">Столбец имеет два типа данных: фактический и определяемый пользователем.</span><span class="sxs-lookup"><span data-stu-id="1b834-119">A column has two data types: its actual data type and its user-defined data type.</span></span> <span data-ttu-id="1b834-120">Определяемый пользователем тип данных используется [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] для хранения фактического определяемого пользователем типа данных столбца, если таковые имеются, и сведения о описании столбца, такие как допустимость значений NULL и возможность обновления для столбца.</span><span class="sxs-lookup"><span data-stu-id="1b834-120">The user-defined data type is used by [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] to store the actual user-defined data type of the column, if any, and column description information, such as nullability and updatability, for the column.</span></span>  
  
 <span data-ttu-id="1b834-121">Функцию **srv_setutype** можно вызвать в любое время после определения *column* с помощью функции **srv_describe** и до передачи последней строки.</span><span class="sxs-lookup"><span data-stu-id="1b834-121">The **srv_setutype** function can be called any time that *column* has been defined with **srv_describe** and before the last row has been sent.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="1b834-122">Необходимо тщательно просмотреть исходный код расширенных хранимых процедур и проверить скомпилированные библиотеки DLL перед их установкой на рабочий сервер.</span><span class="sxs-lookup"><span data-stu-id="1b834-122">You should thoroughly review the source code of extended stored procedures, and you should test the compiled DLLs before you install them on a production server.</span></span> <span data-ttu-id="1b834-123">Сведения о проверке безопасности см. на следующем [веб-сайте Майкрософт](https://go.microsoft.com/fwlink/?LinkID=54761&amp;clcid=0x409https://msdn.microsoft.com/security/).</span><span class="sxs-lookup"><span data-stu-id="1b834-123">For information about security review and testing, see this [Microsoft Web site](https://go.microsoft.com/fwlink/?LinkID=54761&amp;clcid=0x409https://msdn.microsoft.com/security/).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1b834-124">См. также:</span><span class="sxs-lookup"><span data-stu-id="1b834-124">See Also</span></span>  
 [<span data-ttu-id="1b834-125">srv_describe (интерфейс API расширенных хранимых процедур)</span><span class="sxs-lookup"><span data-stu-id="1b834-125">srv_describe &#40;Extended Stored Procedure API&#41;</span></span>](srv-describe-extended-stored-procedure-api.md)  
  
  
