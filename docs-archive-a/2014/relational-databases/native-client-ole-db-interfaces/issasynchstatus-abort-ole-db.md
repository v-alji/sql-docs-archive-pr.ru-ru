---
title: ISSAsynchStatus::Abort (OLE DB) | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
api_name:
- ISSAsynchStatus::Abort (OLE DB)
topic_type:
- apiref
helpviewer_keywords:
- Abort method
ms.assetid: 2a4bd312-839a-45a8-a299-fc8609be9a2a
author: rothja
ms.author: jroth
ms.openlocfilehash: 0fb352b6541240126dcd4c60521b93d57d6839f8
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87734050"
---
# <a name="issasynchstatusabort-ole-db"></a><span data-ttu-id="3a467-102">ISSAsynchStatus::Abort (OLE DB)</span><span class="sxs-lookup"><span data-stu-id="3a467-102">ISSAsynchStatus::Abort (OLE DB)</span></span>
  <span data-ttu-id="3a467-103">Отменяет операцию асинхронного выполнения.</span><span class="sxs-lookup"><span data-stu-id="3a467-103">Cancels an asynchronously executing operation.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3a467-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="3a467-104">Syntax</span></span>  
  
```  
  
HRESULT Abort(  
  HCHAPTER hChapter,  
  DBASYNCHOP eOperation);  
```  
  
## <a name="arguments"></a><span data-ttu-id="3a467-105">Аргументы</span><span class="sxs-lookup"><span data-stu-id="3a467-105">Arguments</span></span>  
 <span data-ttu-id="3a467-106">*hChapter*[in]</span><span class="sxs-lookup"><span data-stu-id="3a467-106">*hChapter*[in]</span></span>  
 <span data-ttu-id="3a467-107">Дескриптор раздела, для которого прерывается операция.</span><span class="sxs-lookup"><span data-stu-id="3a467-107">The handle of the chapter for which to abort the operation.</span></span> <span data-ttu-id="3a467-108">Если вызываемый объект не является объектом набора строк или операция не применяется к разделу, вызывающий должен установить параметру *hChapter* значение DB_NULL_HCHAPTER.</span><span class="sxs-lookup"><span data-stu-id="3a467-108">If the object being called is not a rowset object or the operation does not apply to a chapter, the caller must set *hChapter* to DB_NULL_HCHAPTER.</span></span>  
  
 <span data-ttu-id="3a467-109">*eOperation*[in]</span><span class="sxs-lookup"><span data-stu-id="3a467-109">*eOperation*[in]</span></span>  
 <span data-ttu-id="3a467-110">Операция, которая должна быть прервана.</span><span class="sxs-lookup"><span data-stu-id="3a467-110">The operation to abort.</span></span> <span data-ttu-id="3a467-111">Это должно быть следующее значение.</span><span class="sxs-lookup"><span data-stu-id="3a467-111">This should be the following value:</span></span>  
  
 <span data-ttu-id="3a467-112">DBASYNCHOP_OPEN — запрос на отмену применяется к асинхронному открытию или заполнению набора строк или асинхронной инициализации объекта источника данных.</span><span class="sxs-lookup"><span data-stu-id="3a467-112">DBASYNCHOP_OPEN-The request to cancel applies to the asynchronous opening or population of a rowset or to the asynchronous initialization of a data source object.</span></span>  
  
## <a name="return-code-values"></a><span data-ttu-id="3a467-113">Значения кода возврата</span><span class="sxs-lookup"><span data-stu-id="3a467-113">Return Code Values</span></span>  
 <span data-ttu-id="3a467-114">S_OK</span><span class="sxs-lookup"><span data-stu-id="3a467-114">S_OK</span></span>  
 <span data-ttu-id="3a467-115">Запрос на отмену асинхронной операции обработан.</span><span class="sxs-lookup"><span data-stu-id="3a467-115">The request to cancel the asynchronous operation was processed.</span></span> <span data-ttu-id="3a467-116">Это не гарантирует, что сама операция была отменена.</span><span class="sxs-lookup"><span data-stu-id="3a467-116">This does not guarantee that the operation itself was canceled.</span></span> <span data-ttu-id="3a467-117">Чтобы определить, отменена ли операция, потребитель должен вызвать метод [ISSAsynchStatus::GetStatus](issasynchstatus-getstatus-ole-db.md) и проверить наличие DB_E_CANCELED; однако это значение может быть не возвращено уже в следующем вызове.</span><span class="sxs-lookup"><span data-stu-id="3a467-117">To determine whether the operation was canceled, the consumer should call [ISSAsynchStatus::GetStatus](issasynchstatus-getstatus-ole-db.md) and check for DB_E_CANCELED; however, it might not be returned in the very next call.</span></span>  
  
 <span data-ttu-id="3a467-118">DB_E_CANTCANCEL</span><span class="sxs-lookup"><span data-stu-id="3a467-118">DB_E_CANTCANCEL</span></span>  
 <span data-ttu-id="3a467-119">Асинхронную операцию невозможно отменить.</span><span class="sxs-lookup"><span data-stu-id="3a467-119">The asynchronous operation cannot be canceled.</span></span>  
  
 <span data-ttu-id="3a467-120">DB_E_CANCELED</span><span class="sxs-lookup"><span data-stu-id="3a467-120">DB_E_CANCELED</span></span>  
 <span data-ttu-id="3a467-121">Запрос на прерывание асинхронной операции был отменен во время отправки уведомлений.</span><span class="sxs-lookup"><span data-stu-id="3a467-121">The request to abort the asynchronous operation was canceled during notifications.</span></span> <span data-ttu-id="3a467-122">Операция все еще выполняется асинхронно.</span><span class="sxs-lookup"><span data-stu-id="3a467-122">The operation is still being executed asynchronously.</span></span>  
  
 <span data-ttu-id="3a467-123">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="3a467-123">E_FAIL</span></span>  
 <span data-ttu-id="3a467-124">Произошла ошибка, зависящая от поставщика.</span><span class="sxs-lookup"><span data-stu-id="3a467-124">A provider-specific error occurred.</span></span>  
  
 <span data-ttu-id="3a467-125">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="3a467-125">E_INVALIDARG</span></span>  
 <span data-ttu-id="3a467-126">Значение параметра *hChapter* не равно DB_NULL_HCHAPTER или значение параметра *eOperation* не равно DBASYNCH_OPEN.</span><span class="sxs-lookup"><span data-stu-id="3a467-126">The *hChapter* parameter is not DB_NULL_HCHAPTER or *eOperation* is not DBASYNCH_OPEN.</span></span>  
  
 <span data-ttu-id="3a467-127">E_UNEXPECTED</span><span class="sxs-lookup"><span data-stu-id="3a467-127">E_UNEXPECTED</span></span>  
 <span data-ttu-id="3a467-128">Метод**ISSAsynchStatus::Abort** был вызван для объекта источника данных, для которого не был вызван метод **IDBInitialize::Initialize** .</span><span class="sxs-lookup"><span data-stu-id="3a467-128">**ISSAsynchStatus::Abort** was called on a data source object on which **IDBInitialize::Initialize** has not been called, or has not completed.</span></span>  
  
 <span data-ttu-id="3a467-129">**Метод ISSAsynchStatus:: Abort** был вызван для объекта источника данных, для которого была вызвана **IDBInitialize:: Initialize** , но впоследствии была отменена до инициализации или истекло время ожидания. Объект источника данных все еще не инициализирован.</span><span class="sxs-lookup"><span data-stu-id="3a467-129">**ISSAsynchStatus::Abort** was called on a data source object on which **IDBInitialize::Initialize** was called but subsequently canceled before initialization, or has timed out. The data source object is still uninitialized.</span></span>  
  
 <span data-ttu-id="3a467-130">Интерфейс**ISSAsynchStatus::Abилиt** был вызван для набора строк, для которого ранее был вызван интерфейс **ITransaction::Commit** или **ITransaction::Abилиt** was previously called, and the rowset did not survive the commit или abилиt and is in a zombie state.</span><span class="sxs-lookup"><span data-stu-id="3a467-130">**ISSAsynchStatus::Abort** was called on a rowset on which **ITransaction::Commit** or **ITransaction::Abort** was previously called, and the rowset did not survive the commit or abort and is in a zombie state.</span></span>  
  
 <span data-ttu-id="3a467-131">Интерфейс**ISSAsynchStatus::Abort** был вызван для набора строк, который был асинхронно отменен на стадии его инициализации.</span><span class="sxs-lookup"><span data-stu-id="3a467-131">**ISSAsynchStatus::Abort** was called on a rowset that was asynchronously canceled in its initialization phase.</span></span> <span data-ttu-id="3a467-132">Набор строк находится в состоянии зомби.</span><span class="sxs-lookup"><span data-stu-id="3a467-132">The rowset is in a zombie state.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="3a467-133">Remarks</span><span class="sxs-lookup"><span data-stu-id="3a467-133">Remarks</span></span>  
 <span data-ttu-id="3a467-134">При прерывании инициализации набора строк или объекта источника данных набор строк или объект источника данных может перейти в состояние зомби, когда все методы, кроме методов **IUnknown** , возвращают E_UNEXPECTED.</span><span class="sxs-lookup"><span data-stu-id="3a467-134">Aborting the initialization of a rowset or data source object might leave the rowset or data source object in a zombie state, such that all methods other than **IUnknown** methods return E_UNEXPECTED.</span></span> <span data-ttu-id="3a467-135">В этом случае единственным возможным для потребителя действием является освобождение набора строк или объекта источника данных.</span><span class="sxs-lookup"><span data-stu-id="3a467-135">When this happens, the only possible action for the consumer is to release the rowset or data source object.</span></span>  
  
 <span data-ttu-id="3a467-136">При вызове интерфейса **ISSAsynchStatus::Abort** и передаче параметру *eOperation* значения, отличного от DBASYNCHOP_OPEN, возвращается S_OK.</span><span class="sxs-lookup"><span data-stu-id="3a467-136">Calling **ISSAsynchStatus::Abort** and passing a value for *eOperation* other than DBASYNCHOP_OPEN returns S_OK.</span></span> <span data-ttu-id="3a467-137">Это не подразумевает, что сама операция была завершена или отменена.</span><span class="sxs-lookup"><span data-stu-id="3a467-137">This does not imply that the operation completed or was canceled.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3a467-138">См. также:</span><span class="sxs-lookup"><span data-stu-id="3a467-138">See Also</span></span>  
 [<span data-ttu-id="3a467-139">Выполнение асинхронных операций</span><span class="sxs-lookup"><span data-stu-id="3a467-139">Performing Asynchronous Operations</span></span>](../native-client/features/performing-asynchronous-operations.md)  
  
  
