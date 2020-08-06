---
title: srv_setcoldata (интерфейс API расширенных хранимых процедур) | Документы Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: stored-procedures
ms.topic: reference
api_name:
- srv_setcoldata
api_location:
- opends60.dll
topic_type:
- apiref
dev_langs:
- C++
helpviewer_keywords:
- srv_setcoldata
ms.assetid: 2e19205a-25ca-4d4a-916b-d591cf2c892b
author: rothja
ms.author: jroth
ms.openlocfilehash: b67aa2f7b5a37057d2ed87846689919d84ec4aaf
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87739986"
---
# <a name="srv_setcoldata-extended-stored-procedure-api"></a><span data-ttu-id="0e3da-102">srv_setcoldata (API-интерфейс расширенных хранимых процедур)</span><span class="sxs-lookup"><span data-stu-id="0e3da-102">srv_setcoldata (Extended Stored Procedure API)</span></span>
    
> [!IMPORTANT]  
>  [!INCLUDE[ssNoteDepFutureDontUse](../../includes/ssnotedepfuturedontuse-md.md)] <span data-ttu-id="0e3da-103">Используйте вместо этого интеграцию со средой CLR.</span><span class="sxs-lookup"><span data-stu-id="0e3da-103">Use CLR integration instead.</span></span>  
  
 <span data-ttu-id="0e3da-104">Указывает текущий адрес для данных столбца.</span><span class="sxs-lookup"><span data-stu-id="0e3da-104">Specifies the current address for a column's data.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0e3da-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="0e3da-105">Syntax</span></span>  
  
```  
  
int srv_setcoldata (  
SRV_PROC *  
srvproc  
,  
int   
column  
,  
void *  
data   
);  
  
```  
  
## <a name="arguments"></a><span data-ttu-id="0e3da-106">Аргументы</span><span class="sxs-lookup"><span data-stu-id="0e3da-106">Arguments</span></span>  
 <span data-ttu-id="0e3da-107">*srvproc*</span><span class="sxs-lookup"><span data-stu-id="0e3da-107">*srvproc*</span></span>  
 <span data-ttu-id="0e3da-108">Указатель на структуру SRV_PROC, который представляет собой дескриптор соединения с клиентом.</span><span class="sxs-lookup"><span data-stu-id="0e3da-108">Is a pointer to the SRV_PROC structure that is the handle for a particular client connection.</span></span> <span data-ttu-id="0e3da-109">Эта структура содержит сведения, которые используются библиотекой API-интерфейса расширенных хранимых процедур для управления связью и передачи данных между приложением и клиентом.</span><span class="sxs-lookup"><span data-stu-id="0e3da-109">The structure contains information the Extended Stored Procedure API library uses to manage communication and data between the application and the client.</span></span>  
  
 <span data-ttu-id="0e3da-110">*column*</span><span class="sxs-lookup"><span data-stu-id="0e3da-110">*column*</span></span>  
 <span data-ttu-id="0e3da-111">Указывает номер столбца, для которого задается адрес.</span><span class="sxs-lookup"><span data-stu-id="0e3da-111">Indicates the number of the column the address is being specified for.</span></span> <span data-ttu-id="0e3da-112">Нумерация столбцов начинается с 1.</span><span class="sxs-lookup"><span data-stu-id="0e3da-112">Columns are numbered beginning with 1.</span></span>  
  
 <span data-ttu-id="0e3da-113">*data*</span><span class="sxs-lookup"><span data-stu-id="0e3da-113">*data*</span></span>  
 <span data-ttu-id="0e3da-114">Указатель для данных столбца.</span><span class="sxs-lookup"><span data-stu-id="0e3da-114">Is a pointer for a column's data.</span></span> <span data-ttu-id="0e3da-115">Память, выделенная для *data* , не должна освобождаться до замены данных столбца с помощью еще одного вызова метода **srv_setcoldata**или **srv_senddone** .</span><span class="sxs-lookup"><span data-stu-id="0e3da-115">Memory allocated for *data* should not be freed until the column data is replaced by another call to **srv_setcoldata**, or until **srv_senddone** is called.</span></span>  
  
## <a name="returns"></a><span data-ttu-id="0e3da-116">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="0e3da-116">Returns</span></span>  
 <span data-ttu-id="0e3da-117">SUCCEED или FAIL.</span><span class="sxs-lookup"><span data-stu-id="0e3da-117">SUCCEED or FAIL.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="0e3da-118">Remarks</span><span class="sxs-lookup"><span data-stu-id="0e3da-118">Remarks</span></span>  
 <span data-ttu-id="0e3da-119">Каждый столбец строки должен быть сначала определен с помощью метода **srv_describe**.</span><span class="sxs-lookup"><span data-stu-id="0e3da-119">Each column of the row must be defined first with **srv_describe**.</span></span> <span data-ttu-id="0e3da-120">Адреса данных столбцов первоначально задаются с помощью метода **srv_describe**.</span><span class="sxs-lookup"><span data-stu-id="0e3da-120">Column data addresses are initially set with **srv_describe**.</span></span> <span data-ttu-id="0e3da-121">При изменении адреса данных столбца необходимо вызвать метод **srv_setcoldata** , чтобы указать новый адрес данных. Метод **srv_setcoldata** необходимо вызывать для каждого измененного столбца в отдельности.</span><span class="sxs-lookup"><span data-stu-id="0e3da-121">If the address of the column data changes, **srv_setcoldata** must be called to specify the new address of the data and **srv_setcoldata** must be called separately for each changed column.</span></span>  
  
 <span data-ttu-id="0e3da-122">Данные, содержащие значения NULL, представляются путем задания длины столбца в 0 с помощью метода **srv_setcollen**.</span><span class="sxs-lookup"><span data-stu-id="0e3da-122">Null data is represented by setting the column's length to 0 with **srv_setcollen**.</span></span> <span data-ttu-id="0e3da-123">В этом случае адрес данных будет пропущен.</span><span class="sxs-lookup"><span data-stu-id="0e3da-123">The data address is then ignored.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="0e3da-124">Необходимо тщательно просмотреть исходный код расширенных хранимых процедур и проверить скомпилированные библиотеки DLL перед их установкой на рабочий сервер.</span><span class="sxs-lookup"><span data-stu-id="0e3da-124">You should thoroughly review the source code of extended stored procedures, and you should test the compiled DLLs before you install them on a production server.</span></span> <span data-ttu-id="0e3da-125">Сведения о проверке безопасности см. на следующем [веб-сайте Майкрософт](https://go.microsoft.com/fwlink/?LinkID=54761&amp;clcid=0x409https://msdn.microsoft.com/security/).</span><span class="sxs-lookup"><span data-stu-id="0e3da-125">For information about security review and testing, see this [Microsoft Web site](https://go.microsoft.com/fwlink/?LinkID=54761&amp;clcid=0x409https://msdn.microsoft.com/security/).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0e3da-126">См. также:</span><span class="sxs-lookup"><span data-stu-id="0e3da-126">See Also</span></span>  
 [<span data-ttu-id="0e3da-127">srv_describe (интерфейс API расширенных хранимых процедур)</span><span class="sxs-lookup"><span data-stu-id="0e3da-127">srv_describe &#40;Extended Stored Procedure API&#41;</span></span>](srv-describe-extended-stored-procedure-api.md)  
  
  
