---
title: srv_setcollen (интерфейс API расширенных хранимых процедур) | Документы Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: stored-procedures
ms.topic: reference
api_name:
- srv_setcollen
api_location:
- opends60.dll
topic_type:
- apiref
dev_langs:
- C++
helpviewer_keywords:
- srv_setcollen
ms.assetid: 3c60f1c3-4562-463a-a259-12df172788bd
author: rothja
ms.author: jroth
ms.openlocfilehash: 8e3023e2ac239e074656329da7d8af3aba3afa88
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87730685"
---
# <a name="srv_setcollen-extended-stored-procedure-api"></a><span data-ttu-id="a7332-102">srv_setcollen (API-интерфейс расширенных хранимых процедур)</span><span class="sxs-lookup"><span data-stu-id="a7332-102">srv_setcollen (Extended Stored Procedure API)</span></span>
    
> [!IMPORTANT]  
>  [!INCLUDE[ssNoteDepFutureDontUse](../../includes/ssnotedepfuturedontuse-md.md)] <span data-ttu-id="a7332-103">Используйте вместо этого интеграцию со средой CLR.</span><span class="sxs-lookup"><span data-stu-id="a7332-103">Use CLR integration instead.</span></span>  
  
 <span data-ttu-id="a7332-104">Указывает текущую длину данных в байтах столбца переменной длины или столбца, допускающего значения NULL.</span><span class="sxs-lookup"><span data-stu-id="a7332-104">Specifies the current data length in bytes of a variable-length column or a column that allows NULL values.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a7332-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="a7332-105">Syntax</span></span>  
  
```  
  
int srv_setcollen (  
SRV_PROC *  
srvproc  
,  
int   
column  
,  
int  
len   
);  
  
```  
  
## <a name="arguments"></a><span data-ttu-id="a7332-106">Аргументы</span><span class="sxs-lookup"><span data-stu-id="a7332-106">Arguments</span></span>  
 <span data-ttu-id="a7332-107">*srvproc*</span><span class="sxs-lookup"><span data-stu-id="a7332-107">*srvproc*</span></span>  
 <span data-ttu-id="a7332-108">Указатель на структуру SRV_PROC, который представляет собой дескриптор соединения с клиентом.</span><span class="sxs-lookup"><span data-stu-id="a7332-108">Is a pointer to the SRV_PROC structure that is the handle for a particular client connection.</span></span> <span data-ttu-id="a7332-109">Эта структура содержит сведения, которые используются библиотекой API-интерфейса расширенных хранимых процедур для управления связью и передачи данных между приложением и клиентом.</span><span class="sxs-lookup"><span data-stu-id="a7332-109">The structure contains information the Extended Stored Procedure API library uses to manage communication and data between the application and the client.</span></span>  
  
 <span data-ttu-id="a7332-110">*column*</span><span class="sxs-lookup"><span data-stu-id="a7332-110">*column*</span></span>  
 <span data-ttu-id="a7332-111">Указывает номер столбца, для которого задана длина данных.</span><span class="sxs-lookup"><span data-stu-id="a7332-111">Indicates the number of the column for which the data length is being specified.</span></span> <span data-ttu-id="a7332-112">Нумерация столбцов начинается с 1.</span><span class="sxs-lookup"><span data-stu-id="a7332-112">Columns are numbered beginning with 1.</span></span>  
  
 <span data-ttu-id="a7332-113">*len*</span><span class="sxs-lookup"><span data-stu-id="a7332-113">*len*</span></span>  
 <span data-ttu-id="a7332-114">Указывает длину столбца данных в байтах.</span><span class="sxs-lookup"><span data-stu-id="a7332-114">Indicates the length, in bytes, of the column data.</span></span> <span data-ttu-id="a7332-115">Длина 0 означает, что значение данных столбца — NULL.</span><span class="sxs-lookup"><span data-stu-id="a7332-115">A length of 0 means the column data value is null.</span></span>  
  
## <a name="returns"></a><span data-ttu-id="a7332-116">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="a7332-116">Returns</span></span>  
 <span data-ttu-id="a7332-117">SUCCEED или FAIL.</span><span class="sxs-lookup"><span data-stu-id="a7332-117">SUCCEED or FAIL.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a7332-118">Remarks</span><span class="sxs-lookup"><span data-stu-id="a7332-118">Remarks</span></span>  
 <span data-ttu-id="a7332-119">Каждый столбец строки должен сначала быть определен с помощью **srv_describe**.</span><span class="sxs-lookup"><span data-stu-id="a7332-119">Each column of the row must first be defined with **srv_describe**.</span></span> <span data-ttu-id="a7332-120">Длина данных столбца устанавливается последним вызовом к **srv_describe** или **srv_setcollen**.</span><span class="sxs-lookup"><span data-stu-id="a7332-120">The column data length is set by the last call to **srv_describe** or **srv_setcollen**.</span></span> <span data-ttu-id="a7332-121">Если в строке изменяются данные переменной длины (данные, оканчивающиеся нулевым байтом), необходимо использовать **srv_setcollen**, чтобы установить новую длину перед вызовом **srv_sendrow**.</span><span class="sxs-lookup"><span data-stu-id="a7332-121">If variable-length data (null-terminated data) changes for a row, **srv_setcollen** must be used to set it to the new length before calling **srv_sendrow**.</span></span> <span data-ttu-id="a7332-122">Для столбца, в котором разрешены значения NULL, процедура **srv_describe** должна быть вызвана с параметром *desttype*, для которого установлен тип данных, допускающий значения NULL (например, SRVINTN), а данные, которые могут принимать значение NULL, задаются путем вызова процедуры **srv_setcollen** с параметром *len*, установленным в значение 0.</span><span class="sxs-lookup"><span data-stu-id="a7332-122">For a column that allows null values, **srv_describe** must have been called with *desttype* set to a data type that allows nulls (like SRVINTN) and null data is specified by calling **srv_setcollen** with *len* set to 0.</span></span> <span data-ttu-id="a7332-123">Данные с нулевой длиной не могут быть указаны в API-интерфейсе расширенных хранимых процедур.</span><span class="sxs-lookup"><span data-stu-id="a7332-123">Zero length data cannot be specified using the Extended Stored Procedure API.</span></span>  
  
 <span data-ttu-id="a7332-124">Обратите внимание, что если тип данных столбца имеет переменную длину, *len* не проверяется.</span><span class="sxs-lookup"><span data-stu-id="a7332-124">Note that when the data type of the column is variable-length, *len* is not checked.</span></span> <span data-ttu-id="a7332-125">Если эта функция вызвана для столбца переменной длины, то возвращается значение FAIL.</span><span class="sxs-lookup"><span data-stu-id="a7332-125">This function returns FAIL if called for a fixed-length column.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="a7332-126">Необходимо тщательно просмотреть исходный код расширенных хранимых процедур и проверить скомпилированные библиотеки DLL перед их установкой на рабочий сервер.</span><span class="sxs-lookup"><span data-stu-id="a7332-126">You should thoroughly review the source code of extended stored procedures, and you should test the compiled DLLs before you install them on a production server.</span></span> <span data-ttu-id="a7332-127">Сведения о проверке безопасности см. на следующем [веб-сайте Майкрософт](https://go.microsoft.com/fwlink/?LinkID=54761&amp;clcid=0x409https://msdn.microsoft.com/security/).</span><span class="sxs-lookup"><span data-stu-id="a7332-127">For information about security review and testing, see this [Microsoft Web site](https://go.microsoft.com/fwlink/?LinkID=54761&amp;clcid=0x409https://msdn.microsoft.com/security/).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a7332-128">См. также:</span><span class="sxs-lookup"><span data-stu-id="a7332-128">See Also</span></span>  
 [<span data-ttu-id="a7332-129">srv_describe (интерфейс API расширенных хранимых процедур)</span><span class="sxs-lookup"><span data-stu-id="a7332-129">srv_describe &#40;Extended Stored Procedure API&#41;</span></span>](srv-describe-extended-stored-procedure-api.md)  
  
  
