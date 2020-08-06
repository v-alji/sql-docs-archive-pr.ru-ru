---
title: srv_paramsetoutput (интерфейс API расширенных хранимых процедур) | Документы Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: stored-procedures
ms.topic: reference
api_name:
- srv_paramsetoutput
api_location:
- opends60.dll
topic_type:
- apiref
dev_langs:
- C++
helpviewer_keywords:
- srv_paramsetoutput
ms.assetid: f2810e19-e513-458b-8925-5756b6ee1313
author: rothja
ms.author: jroth
ms.openlocfilehash: 2847367fe5d6052728cebf30467b68cb14fb8e63
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87655728"
---
# <a name="srv_paramsetoutput-extended-stored-procedure-api"></a><span data-ttu-id="f2d53-102">srv_paramsetoutput (API-интерфейс расширенных хранимых процедур)</span><span class="sxs-lookup"><span data-stu-id="f2d53-102">srv_paramsetoutput (Extended Stored Procedure API)</span></span>
    
> [!IMPORTANT]  
>  [!INCLUDE[ssNoteDepFutureDontUse](../../includes/ssnotedepfuturedontuse-md.md)] <span data-ttu-id="f2d53-103">Используйте вместо этого интеграцию со средой CLR.</span><span class="sxs-lookup"><span data-stu-id="f2d53-103">Use CLR integration instead.</span></span>  
  
 <span data-ttu-id="f2d53-104">Устанавливает значение возвращаемого параметра.</span><span class="sxs-lookup"><span data-stu-id="f2d53-104">Sets the value of a return parameter.</span></span> <span data-ttu-id="f2d53-105">Эта функция заменяет функцию **srv_paramset**.</span><span class="sxs-lookup"><span data-stu-id="f2d53-105">This function supersedes the **srv_paramset** function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f2d53-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="f2d53-106">Syntax</span></span>  
  
```  
  
int srv_paramsetoutput (  
SRV_PROC *  
srvproc  
,  
int  
n  
,  
BYTE *  
pbData  
,  
ULONG   
cbLen  
,  
BOOL  
fNull   
);  
  
```  
  
## <a name="arguments"></a><span data-ttu-id="f2d53-107">Аргументы</span><span class="sxs-lookup"><span data-stu-id="f2d53-107">Arguments</span></span>  
 <span data-ttu-id="f2d53-108">*srvproc*</span><span class="sxs-lookup"><span data-stu-id="f2d53-108">*srvproc*</span></span>  
 <span data-ttu-id="f2d53-109">Является дескриптором клиентского соединения.</span><span class="sxs-lookup"><span data-stu-id="f2d53-109">Is a handle for a client connection.</span></span>  
  
 <span data-ttu-id="f2d53-110">*n*</span><span class="sxs-lookup"><span data-stu-id="f2d53-110">*n*</span></span>  
 <span data-ttu-id="f2d53-111">Является порядковым номером параметра, который должен быть установлен.</span><span class="sxs-lookup"><span data-stu-id="f2d53-111">Is the ordinal number of the parameter to be set.</span></span> <span data-ttu-id="f2d53-112">Первый параметр имеет значение 1.</span><span class="sxs-lookup"><span data-stu-id="f2d53-112">The first parameter is 1.</span></span>  
  
 <span data-ttu-id="f2d53-113">*pbData*</span><span class="sxs-lookup"><span data-stu-id="f2d53-113">*pbData*</span></span>  
 <span data-ttu-id="f2d53-114">Является указателем на значение данных, которое должно быть отправлено обратно клиенту как возвращаемый параметр процедуры.</span><span class="sxs-lookup"><span data-stu-id="f2d53-114">Is a pointer to the data value to be sent back to the client as a procedure return parameter.</span></span>  
  
 <span data-ttu-id="f2d53-115">*cbLen*</span><span class="sxs-lookup"><span data-stu-id="f2d53-115">*cbLen*</span></span>  
 <span data-ttu-id="f2d53-116">Является фактической длиной данных, которые должны быть возвращены.</span><span class="sxs-lookup"><span data-stu-id="f2d53-116">Is the actual length of the data to be returned.</span></span> <span data-ttu-id="f2d53-117">Если тип данных параметра указывает значения постоянной длины и не допускает значений NULL (например, *srvbit* или *srvint1*), аргумент*cbLen* не учитывается.</span><span class="sxs-lookup"><span data-stu-id="f2d53-117">If the data type of the parameter specifies values of a constant length and does not allow null values (for example, *srvbit* or *srvint1*), *cbLen* is ignored.</span></span> <span data-ttu-id="f2d53-118">Значение, равное 0, указывает на данные нулевой длины, если значение *fNull* равно FALSE.</span><span class="sxs-lookup"><span data-stu-id="f2d53-118">A value of 0 signifies zero-length data if *fNull* is FALSE.</span></span>  
  
 <span data-ttu-id="f2d53-119">*fNull*</span><span class="sxs-lookup"><span data-stu-id="f2d53-119">*fNull*</span></span>  
 <span data-ttu-id="f2d53-120">Является флагом, показывающим, равно ли NULL значение возвращаемого параметра.</span><span class="sxs-lookup"><span data-stu-id="f2d53-120">Is a flag indicating whether the value of the return parameter is NULL.</span></span> <span data-ttu-id="f2d53-121">Установите этот флаг в значение TRUE, если параметр должен быть установлен в значение NULL.</span><span class="sxs-lookup"><span data-stu-id="f2d53-121">Set this flag to TRUE if the parameter should be set to NULL.</span></span> <span data-ttu-id="f2d53-122">Значение по умолчанию — FALSE.</span><span class="sxs-lookup"><span data-stu-id="f2d53-122">The default value is FALSE.</span></span> <span data-ttu-id="f2d53-123">Если *fNull* установлен в значение TRUE, то аргумент *cbLen* должен быть установлен в значение 0, иначе функция завершится с ошибкой.</span><span class="sxs-lookup"><span data-stu-id="f2d53-123">If *fNull* is set to TRUE, *cbLen* should be set to 0 or the function will fail.</span></span>  
  
## <a name="returns"></a><span data-ttu-id="f2d53-124">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="f2d53-124">Returns</span></span>  
 <span data-ttu-id="f2d53-125">Если сведения о параметре были успешно установлены, возвращается значение SUCCEED, в противном случае — FAIL.</span><span class="sxs-lookup"><span data-stu-id="f2d53-125">If the parameter information was successfully set, SUCCEED is returned; otherwise, FAIL.</span></span> <span data-ttu-id="f2d53-126">Значение FAIL возвращается, если:</span><span class="sxs-lookup"><span data-stu-id="f2d53-126">FAIL is returned when</span></span>  
  
-   <span data-ttu-id="f2d53-127">параметр не является возвращаемым параметром, или</span><span class="sxs-lookup"><span data-stu-id="f2d53-127">the parameter is not a return parameter, or</span></span>  
  
-   <span data-ttu-id="f2d53-128">аргумент *cbLen* недопустим.</span><span class="sxs-lookup"><span data-stu-id="f2d53-128">the *cbLen* argument is invalid.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f2d53-129">Remarks</span><span class="sxs-lookup"><span data-stu-id="f2d53-129">Remarks</span></span>  
 <span data-ttu-id="f2d53-130">**Примечание по безопасности.** Необходимо тщательно просмотреть исходный код расширенных хранимых процедур и проверить скомпилированные DLL-библиотеки перед их установкой на рабочий сервер.</span><span class="sxs-lookup"><span data-stu-id="f2d53-130">**Security Note** You should thoroughly review the source code of extended stored procedures, and you should test the compiled DLLs before you install them on a production server.</span></span> <span data-ttu-id="f2d53-131">Сведения о проверке безопасности см. на следующем [веб-сайте Майкрософт](https://go.microsoft.com/fwlink/?LinkID=54761&amp;clcid=0x409https://msdn.microsoft.com/security/).</span><span class="sxs-lookup"><span data-stu-id="f2d53-131">For information about security review and testing, see this [Microsoft Web site](https://go.microsoft.com/fwlink/?LinkID=54761&amp;clcid=0x409https://msdn.microsoft.com/security/).</span></span>  
  
  
