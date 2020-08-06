---
title: srv_paraminfo (интерфейс API расширенных хранимых процедур) | Документы Майкрософт
ms.custom: ''
ms.date: 03/08/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: stored-procedures
ms.topic: reference
api_name:
- srv_paraminfo
api_location:
- opends60.dll
topic_type:
- apiref
dev_langs:
- C++
helpviewer_keywords:
- srv_paraminfo
ms.assetid: ee2afd4e-0d91-462b-9403-98d481546330
author: rothja
ms.author: jroth
ms.openlocfilehash: cc3d51acc2ca560246c46267840db72934223999
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87751036"
---
# <a name="srv_paraminfo-extended-stored-procedure-api"></a><span data-ttu-id="84c69-102">srv_paraminfo (API-интерфейс расширенных хранимых процедур)</span><span class="sxs-lookup"><span data-stu-id="84c69-102">srv_paraminfo (Extended Stored Procedure API)</span></span>
    
> [!IMPORTANT]  
>  [!INCLUDE[ssNoteDepFutureDontUse](../../includes/ssnotedepfuturedontuse-md.md)] <span data-ttu-id="84c69-103">Используйте вместо этого интеграцию со средой CLR.</span><span class="sxs-lookup"><span data-stu-id="84c69-103">Use CLR integration instead.</span></span>  
  
 <span data-ttu-id="84c69-104">Возвращает сведения о параметре.</span><span class="sxs-lookup"><span data-stu-id="84c69-104">Returns information about a parameter.</span></span> <span data-ttu-id="84c69-105">Эта функция заменяет следующие: [srv_paramtype](srv-paramtype-extended-stored-procedure-api.md), [srv_paramlen](srv-paramlen-extended-stored-procedure-api.md), [srv_parammaxlen](srv-parammaxlen-extended-stored-procedure-api.md) и [srv_paramdata](srv-paramdata-extended-stored-procedure-api.md).</span><span class="sxs-lookup"><span data-stu-id="84c69-105">This function supersedes the following functions: [srv_paramtype](srv-paramtype-extended-stored-procedure-api.md), [srv_paramlen](srv-paramlen-extended-stored-procedure-api.md), [srv_parammaxlen](srv-parammaxlen-extended-stored-procedure-api.md), and [srv_paramdata](srv-paramdata-extended-stored-procedure-api.md).</span></span> <span data-ttu-id="84c69-106">**srv_paraminfo** поддерживает типы данных, указанные в разделе [Типы данных](data-types-extended-stored-procedure-api.md), и данные нулевой длины.</span><span class="sxs-lookup"><span data-stu-id="84c69-106">**srv_paraminfo** supports the data types in [Data Types](data-types-extended-stored-procedure-api.md) and zero-length data.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="84c69-107">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="84c69-107">Syntax</span></span>  
  
```  
  
int srv_paraminfo (  
SRV_PROC *  
srvproc  
,  
int  
n  
,  
BYTE *  
pbType  
,  
ULONG *  
pcbMaxLen  
,  
ULONG *  
pcbActualLen  
,  
BYTE *  
pbData  
,  
BOOL *  
pfNull  
);  
  
```  
  
## <a name="arguments"></a><span data-ttu-id="84c69-108">Аргументы</span><span class="sxs-lookup"><span data-stu-id="84c69-108">Arguments</span></span>  
 <span data-ttu-id="84c69-109">*srvproc*</span><span class="sxs-lookup"><span data-stu-id="84c69-109">*srvproc*</span></span>  
 <span data-ttu-id="84c69-110">Дескриптор для клиентского соединения.</span><span class="sxs-lookup"><span data-stu-id="84c69-110">A handle for a client connection.</span></span>  
  
 <span data-ttu-id="84c69-111">*n*</span><span class="sxs-lookup"><span data-stu-id="84c69-111">*n*</span></span>  
 <span data-ttu-id="84c69-112">Порядковый номер устанавливаемого столбца.</span><span class="sxs-lookup"><span data-stu-id="84c69-112">The ordinal number of the parameter to be set.</span></span> <span data-ttu-id="84c69-113">Первый параметр имеет значение 1.</span><span class="sxs-lookup"><span data-stu-id="84c69-113">The first parameter is 1.</span></span>  
  
 <span data-ttu-id="84c69-114">*pbType*</span><span class="sxs-lookup"><span data-stu-id="84c69-114">*pbType*</span></span>  
 <span data-ttu-id="84c69-115">Тип данных параметра.</span><span class="sxs-lookup"><span data-stu-id="84c69-115">The data type of the parameter.</span></span>  
  
 <span data-ttu-id="84c69-116">*pcbMaxLen*</span><span class="sxs-lookup"><span data-stu-id="84c69-116">*pcbMaxLen*</span></span>  
 <span data-ttu-id="84c69-117">Указатель на максимальную длину параметра.</span><span class="sxs-lookup"><span data-stu-id="84c69-117">Pointer to the maximum length of the parameter.</span></span>  
  
 <span data-ttu-id="84c69-118">*pcbActualLen*</span><span class="sxs-lookup"><span data-stu-id="84c69-118">*pcbActualLen*</span></span>  
 <span data-ttu-id="84c69-119">Указатель на фактическую длину параметра.</span><span class="sxs-lookup"><span data-stu-id="84c69-119">Pointer to the actual length of the parameter.</span></span> <span data-ttu-id="84c69-120">Значение 0 (\**pcbActualLen* == 0) указывает на данные нулевой длины, если значение \**pfNull* равно FALSE.</span><span class="sxs-lookup"><span data-stu-id="84c69-120">A value of 0 (\**pcbActualLen* == 0) signifies zero-length data if \**pfNull* is set to FALSE.</span></span>  
  
 <span data-ttu-id="84c69-121">*pbData*</span><span class="sxs-lookup"><span data-stu-id="84c69-121">*pbData*</span></span>  
 <span data-ttu-id="84c69-122">Указатель на буфер данных параметра.</span><span class="sxs-lookup"><span data-stu-id="84c69-122">Pointer to the buffer for parameter data.</span></span> <span data-ttu-id="84c69-123">Если значение *pbData* не равно NULL, интерфейс API расширенных хранимых процедур записывает \**pcbActualLen* байт данных в \**pbData*.</span><span class="sxs-lookup"><span data-stu-id="84c69-123">If *pbData* is not NULL, the Extended Store Procedure API writes \**pcbActualLen* bytes of data to \**pbData*.</span></span> <span data-ttu-id="84c69-124">Если *pbData* имеет значение NULL, данные в \**pbData* не записываются, но функция возвращает \**pbType*, \**pcbMaxLen*, \**pcbActualLen* и \**pfNull*.</span><span class="sxs-lookup"><span data-stu-id="84c69-124">If *pbData* is NULL, no data is written to \**pbData* but the function returns \**pbType*, \**pcbMaxLen*, \**pcbActualLen*, and \**pfNull*.</span></span> <span data-ttu-id="84c69-125">Управление памятью для этого буфера должно осуществляться приложением.</span><span class="sxs-lookup"><span data-stu-id="84c69-125">The memory for this buffer must be managed by the application.</span></span>  
  
 <span data-ttu-id="84c69-126">*pfNull*</span><span class="sxs-lookup"><span data-stu-id="84c69-126">*pfNull*</span></span>  
 <span data-ttu-id="84c69-127">Указатель на флаг null</span><span class="sxs-lookup"><span data-stu-id="84c69-127">Pointer to a null flag.</span></span><span data-ttu-id="84c69-128">\ **pfNull* устанавливается в значение TRUE, если параметр имеет значение NULL.</span><span class="sxs-lookup"><span data-stu-id="84c69-128">\ **pfNull* is set to TRUE if the value of the parameter is NULL.</span></span>  
  
## <a name="returns"></a><span data-ttu-id="84c69-129">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="84c69-129">Returns</span></span>  
 <span data-ttu-id="84c69-130">При успешном получении сведений о параметре возвращается значение SUCCEED; в иных случаях – значение FAIL.</span><span class="sxs-lookup"><span data-stu-id="84c69-130">If the parameter information was successfully obtained, SUCCEED is returned; otherwise, FAIL.</span></span> <span data-ttu-id="84c69-131">Значение FAIL возвращается, если удаленной хранимой процедуры сейчас не существует или у нее нет параметра с номером *n*.</span><span class="sxs-lookup"><span data-stu-id="84c69-131">FAIL is returned when there is no current remote stored procedure and when there is no *n*th remote stored procedure parameter.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="84c69-132">Remarks</span><span class="sxs-lookup"><span data-stu-id="84c69-132">Remarks</span></span>  
 <span data-ttu-id="84c69-133">**Примечание по безопасности.** Необходимо тщательно просмотреть исходный код расширенных хранимых процедур и проверить скомпилированные DLL-библиотеки перед их установкой на рабочий сервер.</span><span class="sxs-lookup"><span data-stu-id="84c69-133">**Security Note** You should thoroughly review the source code of extended stored procedures, and you should test the compiled DLLs before you install them on a production server.</span></span> <span data-ttu-id="84c69-134">Сведения о проверке безопасности см. на следующем [веб-сайте Майкрософт](https://go.microsoft.com/fwlink/?LinkID=54761&amp;clcid=0x409https://msdn.microsoft.com/security/).</span><span class="sxs-lookup"><span data-stu-id="84c69-134">For information about security review and testing, see this [Microsoft Web site](https://go.microsoft.com/fwlink/?LinkID=54761&amp;clcid=0x409https://msdn.microsoft.com/security/).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="84c69-135">См. также:</span><span class="sxs-lookup"><span data-stu-id="84c69-135">See Also</span></span>  
 [<span data-ttu-id="84c69-136">Справочник по программированию расширенных хранимых процедур</span><span class="sxs-lookup"><span data-stu-id="84c69-136">Extended Stored Procedures Programmer's Reference</span></span>](database-engine-extended-stored-procedures-reference.md)  
  
  
