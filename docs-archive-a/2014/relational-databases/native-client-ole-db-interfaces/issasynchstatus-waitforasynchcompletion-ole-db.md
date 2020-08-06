---
title: ISSAsynchStatus::WaitForAsynchCompletion (OLE DB) | Документация Майкрософт
ms.custom: ''
ms.date: 06/14/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
api_name:
- ISSAsynchStatus::WaitForAsynchCompletion (OLE DB)
topic_type:
- apiref
helpviewer_keywords:
- WaitForAsynchCompletion method
ms.assetid: 9f65e9e7-eb93-47a1-bc42-acd4649fbd0e
author: rothja
ms.author: jroth
ms.openlocfilehash: f57211d1c62535828704dc971e345b412c284cf1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87657753"
---
# <a name="issasynchstatuswaitforasynchcompletion-ole-db"></a><span data-ttu-id="f2465-102">ISSAsynchStatus::WaitForAsynchCompletion (OLE DB)</span><span class="sxs-lookup"><span data-stu-id="f2465-102">ISSAsynchStatus::WaitForAsynchCompletion (OLE DB)</span></span>
  <span data-ttu-id="f2465-103">Ожидает завершения асинхронно выполняющейся операции или истечения времени ожидания.</span><span class="sxs-lookup"><span data-stu-id="f2465-103">Waits until the asynchronously executing operation is complete or until a time-out occurs.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f2465-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="f2465-104">Syntax</span></span>  
  
```  
  
HRESULT WaitForAsynchCompletion(   
  DWORD dwMillisecTimeOut);  
```  
  
## <a name="arguments"></a><span data-ttu-id="f2465-105">Аргументы</span><span class="sxs-lookup"><span data-stu-id="f2465-105">Arguments</span></span>  
 <span data-ttu-id="f2465-106">*dwMillisecTimeOut*[in]</span><span class="sxs-lookup"><span data-stu-id="f2465-106">*dwMillisecTimeOut*[in]</span></span>  
 <span data-ttu-id="f2465-107">Время ожидания в миллисекундах.</span><span class="sxs-lookup"><span data-stu-id="f2465-107">Time-out in milliseconds.</span></span>  
  
## <a name="return-code-values"></a><span data-ttu-id="f2465-108">Значения кода возврата</span><span class="sxs-lookup"><span data-stu-id="f2465-108">Return Code Values</span></span>  
 <span data-ttu-id="f2465-109">S_OK</span><span class="sxs-lookup"><span data-stu-id="f2465-109">S_OK</span></span>  
 <span data-ttu-id="f2465-110">Метод выполнен успешно.</span><span class="sxs-lookup"><span data-stu-id="f2465-110">The method succeeded.</span></span>  
  
 <span data-ttu-id="f2465-111">E_UNEXPECTED</span><span class="sxs-lookup"><span data-stu-id="f2465-111">E_UNEXPECTED</span></span>  
 <span data-ttu-id="f2465-112">Набор строк находится в неиспользуемом состоянии, поскольку либо был вызван метод **ITransaction::Commit** или **ITransaction::Abort** , либо получение набора строк было отменено при его инициализации.</span><span class="sxs-lookup"><span data-stu-id="f2465-112">A rowset is in an unused state because **ITransaction::Commit** or **ITransaction::Abort** has been called or the rowset was cancelled during its initialization phase.</span></span>  
  
 <span data-ttu-id="f2465-113">DB_E_CANCELED</span><span class="sxs-lookup"><span data-stu-id="f2465-113">DB_E_CANCELED</span></span>  
 <span data-ttu-id="f2465-114">Асинхронная обработка была отменена во время заполнения набора строк или инициализации объекта источника данных.</span><span class="sxs-lookup"><span data-stu-id="f2465-114">Asynchronous processing was cancelled during rowset population or data source object initialization.</span></span>  
  
 <span data-ttu-id="f2465-115">DB_S_ASYNCHRONOUS</span><span class="sxs-lookup"><span data-stu-id="f2465-115">DB_S_ASYNCHRONOUS</span></span>  
 <span data-ttu-id="f2465-116">Операция еще не завершена, хотя истекло заданное время ожидания.</span><span class="sxs-lookup"><span data-stu-id="f2465-116">The operation has not yet completed even though specified time-out has been reached.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="f2465-117">Помимо приведенных выше значений кода возврата, метод **ISSAsynchStatus::WaitForAsynchCompletion** поддерживает также значения, возвращаемые основными методами OLEDB **ICommand::Execute** и **IDBInitialize::Initialize** .</span><span class="sxs-lookup"><span data-stu-id="f2465-117">In addition to the return code values listed above, the **ISSAsynchStatus::WaitForAsynchCompletion** method also supports the return code values returned by the core OLEDB **ICommand::Execute** and **IDBInitialize::Initialize** methods.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f2465-118">Remarks</span><span class="sxs-lookup"><span data-stu-id="f2465-118">Remarks</span></span>  
 <span data-ttu-id="f2465-119">Метод **ISSAsynchStatus::WaitForAsynchCompletion** не возвращает управление до тех пор, пока ему не будет передано значение истечения времени ожидания (в миллисекундах) или пока не завершится отложенная операция.</span><span class="sxs-lookup"><span data-stu-id="f2465-119">The **ISSAsynchStatus::WaitForAsynchCompletion** method will not return until the time-out value (in milliseconds) has passed or the pending operation is done.</span></span> <span data-ttu-id="f2465-120">Объект **Command** имеет свойство **CommandTimeout** , которое управляет количеством секунд, в течение которых запрос будет выполняться до истечения времени ожидания. Свойство **CommandTimeout** будет пропущено, если используется в сочетании с методом **метод ISSAsynchStatus:: WaitForAsynchCompletion** .</span><span class="sxs-lookup"><span data-stu-id="f2465-120">The **Command** object has a **CommandTimeout** property that controls the number of seconds a query will run before timing out. The **CommandTimeout** property will be ignored if used in conjunction with **ISSAsynchStatus::WaitForAsynchCompletion** method.</span></span>  
  
 <span data-ttu-id="f2465-121">Свойство времени ожидания для асинхронных операций не учитывается.</span><span class="sxs-lookup"><span data-stu-id="f2465-121">The time-out property is ignored for asynchronous operations.</span></span> <span data-ttu-id="f2465-122">Параметр истечения времени ожидания **ISSAsynchStatus::WaitForAsynchCompletion** задает максимальное время, которое должно пройти, прежде чем управление будет передано вызывающему объекту.</span><span class="sxs-lookup"><span data-stu-id="f2465-122">The time-out parameter of **ISSAsynchStatus::WaitForAsynchCompletion** specifies the maximum amount of time that will elapse before control is returned to the caller.</span></span> <span data-ttu-id="f2465-123">По истечении этого времени ожидания возвращается значение DB_S_ASYNCHRONOUS.</span><span class="sxs-lookup"><span data-stu-id="f2465-123">If this time-out expires, DB_S_ASYNCHRONOUS will be returned.</span></span> <span data-ttu-id="f2465-124">Время ожидания никогда не отменяет асинхронные операции.</span><span class="sxs-lookup"><span data-stu-id="f2465-124">Time-outs never cancel asynchronous operations.</span></span> <span data-ttu-id="f2465-125">Если приложению необходимо отменить асинхронную операцию, которая не завершена в течение времени ожидания, то оно должно дождаться истечения этого времени, а затем явно отменить операцию, если возвращено значение DB_S_ASYNCHRONOUS.</span><span class="sxs-lookup"><span data-stu-id="f2465-125">If the application needs to cancel an asynchronous operation that does not complete within a time-out period, it must wait for the time-out and then explicitly cancel the operation if DB_S_ASYNCHRONOUS is returned.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="f2465-126">При использовании компонентов службы OLE DB может быть возвращено значение S_OK вместо DB_S_ASYNCHRONOUS, поэтому при возврате одного из этих значений приложение должно вызывать метод [ISSAsynchStatus::GetStatus](issasynchstatus-getstatus-ole-db.md), чтобы проверить состояние завершения операции.</span><span class="sxs-lookup"><span data-stu-id="f2465-126">When the OLE DB Service Components are used, S_OK may be returned when DB_S_ASYNCHRONOUS is expected, so applications should call [ISSAsynchStatus::GetStatus](issasynchstatus-getstatus-ole-db.md) to check for completion when S_OK or DB_S_ASYNCHRONOUS is returned.</span></span>  
  
 <span data-ttu-id="f2465-127">Если параметр *dwMillisecTimeOut* имеет значение INFINITE, то метод **ISSAsynchStatus::WaitForAsynchCompletion** блокируется до завершения операции.</span><span class="sxs-lookup"><span data-stu-id="f2465-127">If the *dwMillisecTimeOut* value is set to INFINITE, the **ISSAsynchStatus::WaitForAsynchCompletion** method blocks until the operation is done.</span></span> <span data-ttu-id="f2465-128">Если параметр *dwMillisecTimeOut* имеет значение 0, то метод немедленно вернет состояние отложенной операции.</span><span class="sxs-lookup"><span data-stu-id="f2465-128">If the *dwMillisecTimeOut* value is set to 0, then the method will return immediately with the status of the pending operation.</span></span> <span data-ttu-id="f2465-129">Если время ожидания истекло до завершения операции, возвращается значение DB_S_ASYNCHRONOUS.</span><span class="sxs-lookup"><span data-stu-id="f2465-129">If the time-out expires before the operation is complete DB_S_ASYNCHRONOUS will be returned.</span></span>  
  
 <span data-ttu-id="f2465-130">Если операция завершится прежде, чем истечет время ожидания, то возвращенное значение будет представлять собой HRESULT операции (то есть HRESULT, который был бы возвращен, если бы операция выполнялась синхронно).</span><span class="sxs-lookup"><span data-stu-id="f2465-130">If the operation completes before the time-out expires, the returned HRESULT will be the HRESULT returned by the operation (the HRESULT that would have been returned had the operation been performed synchronously).</span></span>  
  
 <span data-ttu-id="f2465-131">Кроме того, в набор свойств DBPROPSET_SQLSERVERROWSET добавлено свойство SSPROP_ISSAsynchStatus.</span><span class="sxs-lookup"><span data-stu-id="f2465-131">In addition, the SSPROP_ISSAsynchStatus property has been added to the DBPROPSET_SQLSERVERROWSET property set.</span></span> <span data-ttu-id="f2465-132">Поставщики, поддерживающие интерфейс [ISSAsynchStatus](issasynchstatus-ole-db.md), должны реализовывать это свойство со значением VARIANT_TRUE.</span><span class="sxs-lookup"><span data-stu-id="f2465-132">Providers that support the [ISSAsynchStatus](issasynchstatus-ole-db.md) interface must implement this property with a value of VARIANT_TRUE.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f2465-133">См. также:</span><span class="sxs-lookup"><span data-stu-id="f2465-133">See Also</span></span>  
 <span data-ttu-id="f2465-134">[Выполнение асинхронных операций](../native-client/features/performing-asynchronous-operations.md) </span><span class="sxs-lookup"><span data-stu-id="f2465-134">[Performing Asynchronous Operations](../native-client/features/performing-asynchronous-operations.md) </span></span>  
 [<span data-ttu-id="f2465-135">ISSAsynchStatus (OLE DB)</span><span class="sxs-lookup"><span data-stu-id="f2465-135">ISSAsynchStatus &#40;OLE DB&#41;</span></span>](issasynchstatus-ole-db.md)  
  
  
