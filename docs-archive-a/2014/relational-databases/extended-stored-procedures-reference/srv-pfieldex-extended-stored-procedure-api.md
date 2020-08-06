---
title: srv_pfieldex (интерфейс API расширенных хранимых процедур) | Документы Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: stored-procedures
ms.topic: reference
api_name:
- srv_pfieldex
api_location:
- opends60.dll
topic_type:
- apiref
dev_langs:
- C++
helpviewer_keywords:
- srv_pfieldex
ms.assetid: d4e9a34b-b3a3-434f-8556-768bd20d145a
author: rothja
ms.author: jroth
ms.openlocfilehash: a474eafcb6b6d42161a7e67ce7f93636269c46c7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87657105"
---
# <a name="srv_pfieldex-extended-stored-procedure-api"></a><span data-ttu-id="d046d-102">srv_pfieldex (API-интерфейс расширенных хранимых процедур)</span><span class="sxs-lookup"><span data-stu-id="d046d-102">srv_pfieldex (Extended Stored Procedure API)</span></span>
    
> [!IMPORTANT]  
>  [!INCLUDE[ssNoteDepFutureDontUse](../../includes/ssnotedepfuturedontuse-md.md)] <span data-ttu-id="d046d-103">Используйте вместо этого интеграцию со средой CLR.</span><span class="sxs-lookup"><span data-stu-id="d046d-103">Use CLR integration instead.</span></span>  
  
 <span data-ttu-id="d046d-104">Возвращает указатель на данные, содержащие в запрошенном поле SRV_PROC.</span><span class="sxs-lookup"><span data-stu-id="d046d-104">Returns a pointer to data containing the requested SRV_PROC field.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d046d-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="d046d-105">Syntax</span></span>  
  
```  
  
void *srv_pfieldex(SRV_PROC *   
srvproc  
, int   
field  
, int *   
len  
);  
  
```  
  
## <a name="arguments"></a><span data-ttu-id="d046d-106">Аргументы</span><span class="sxs-lookup"><span data-stu-id="d046d-106">Arguments</span></span>  
 <span data-ttu-id="d046d-107">*srvproc*</span><span class="sxs-lookup"><span data-stu-id="d046d-107">*srvproc*</span></span>  
 <span data-ttu-id="d046d-108">Указатель на структуру SRV_PROC, который представляет собой дескриптор соединения с клиентом.</span><span class="sxs-lookup"><span data-stu-id="d046d-108">Is a pointer to the SRV_PROC structure that is the handle for a particular client connection.</span></span> <span data-ttu-id="d046d-109">Эта структура содержит сведения, которые используются библиотекой API-интерфейса расширенных хранимых процедур для управления связью и передачи данных между приложением и клиентом.</span><span class="sxs-lookup"><span data-stu-id="d046d-109">The structure contains information the Extended Stored Procedure API library uses to manage communication and data between the application and the client.</span></span>  
  
 <span data-ttu-id="d046d-110">*полями*</span><span class="sxs-lookup"><span data-stu-id="d046d-110">*field*</span></span>  
 <span data-ttu-id="d046d-111">Указывает возвращаемое поле *srvproc*.</span><span class="sxs-lookup"><span data-stu-id="d046d-111">Specifies the *srvproc* field to return.</span></span>  
  
|<span data-ttu-id="d046d-112">Поле</span><span class="sxs-lookup"><span data-stu-id="d046d-112">Field</span></span>|<span data-ttu-id="d046d-113">Описание</span><span class="sxs-lookup"><span data-stu-id="d046d-113">Description</span></span>|<span data-ttu-id="d046d-114">Тип возвращаемых данных</span><span class="sxs-lookup"><span data-stu-id="d046d-114">Return-type</span></span>|  
|-----------|-----------------|------------------|  
|<span data-ttu-id="d046d-115">SRV_MSGLCID</span><span class="sxs-lookup"><span data-stu-id="d046d-115">SRV_MSGLCID</span></span>|<span data-ttu-id="d046d-116">Код языка сообщения текущего сеанса.</span><span class="sxs-lookup"><span data-stu-id="d046d-116">Current session message LCID.</span></span>|<span data-ttu-id="d046d-117">ULONG\*</span><span class="sxs-lookup"><span data-stu-id="d046d-117">ULONG\*</span></span>|  
|<span data-ttu-id="d046d-118">SRV_INSTANCENAME</span><span class="sxs-lookup"><span data-stu-id="d046d-118">SRV_INSTANCENAME</span></span>|<span data-ttu-id="d046d-119">Имя экземпляра (для именованного экземпляра), иначе возвращает значение NULL.</span><span class="sxs-lookup"><span data-stu-id="d046d-119">Instance name (if named); otherwise, returns NULL.</span></span>|<span data-ttu-id="d046d-120">WCHAR\*</span><span class="sxs-lookup"><span data-stu-id="d046d-120">WCHAR\*</span></span>|  
  
 <span data-ttu-id="d046d-121">*len*</span><span class="sxs-lookup"><span data-stu-id="d046d-121">*len*</span></span>  
 <span data-ttu-id="d046d-122">Указатель на переменную типа **int**, которая содержит длину возвращенного значения *field* в байтах.</span><span class="sxs-lookup"><span data-stu-id="d046d-122">Is a pointer to an **int** variable that contains the length of the returned *field* value in bytes.</span></span> <span data-ttu-id="d046d-123">Если значение *len* равно NULL, длина не возвращается.</span><span class="sxs-lookup"><span data-stu-id="d046d-123">If *len* is NULL, the length is not returned.</span></span> <span data-ttu-id="d046d-124">Если возвращается значение NULL, то параметру \**len* задается значение 0.</span><span class="sxs-lookup"><span data-stu-id="d046d-124">When NULL is returned \**len* is set to 0.</span></span>  
  
## <a name="returns"></a><span data-ttu-id="d046d-125">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="d046d-125">Returns</span></span>  
 <span data-ttu-id="d046d-126">Указатель на данные, тип которых зависит от *field*.</span><span class="sxs-lookup"><span data-stu-id="d046d-126">A pointer to data whose type depends on *field*.</span></span> <span data-ttu-id="d046d-127">Если *len* имеет значение NULL или *srvproc* имеет значение NULL, возвращается значение NULL.</span><span class="sxs-lookup"><span data-stu-id="d046d-127">NULL is returned when *len* is NULL or *srvproc* is NULL.</span></span> <span data-ttu-id="d046d-128">Если *field* неизвестно, то возвращается значение NULL.</span><span class="sxs-lookup"><span data-stu-id="d046d-128">If the *field* is unknown, NULL is returned.</span></span> <span data-ttu-id="d046d-129">Если возвращается значение NULL, то параметру \**len* задается значение 0.</span><span class="sxs-lookup"><span data-stu-id="d046d-129">When NULL is returned \**len* is set to 0.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="d046d-130">Буфер, возвращенный из сервера, должен быть доступен только для чтения.</span><span class="sxs-lookup"><span data-stu-id="d046d-130">The buffer returned from the server should be read only.</span></span> <span data-ttu-id="d046d-131">В противном случае состояние сервера может быть повреждено.</span><span class="sxs-lookup"><span data-stu-id="d046d-131">Otherwise, the server state may be corrupted.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d046d-132">Remarks</span><span class="sxs-lookup"><span data-stu-id="d046d-132">Remarks</span></span>  
 <span data-ttu-id="d046d-133">**Примечание по безопасности.** Необходимо тщательно просмотреть исходный код расширенных хранимых процедур и проверить скомпилированные DLL-библиотеки перед их установкой на рабочий сервер.</span><span class="sxs-lookup"><span data-stu-id="d046d-133">**Security Note** You should thoroughly review the source code of extended stored procedures, and you should test the compiled DLLs before you install them on a production server.</span></span> <span data-ttu-id="d046d-134">Сведения о проверке безопасности см. на следующем [веб-сайте Майкрософт](https://go.microsoft.com/fwlink/?LinkID=54761&amp;clcid=0x409https://msdn.microsoft.com/security/).</span><span class="sxs-lookup"><span data-stu-id="d046d-134">For information about security review and testing, see this [Microsoft Web site](https://go.microsoft.com/fwlink/?LinkID=54761&amp;clcid=0x409https://msdn.microsoft.com/security/).</span></span>  
  
  
