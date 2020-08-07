---
title: ISSAbort::Abort (OLE DB) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
api_name:
- ISSAbort::Abort (OLE DB)
topic_type:
- apiref
helpviewer_keywords:
- Abort method
ms.assetid: a5bca169-694b-4895-84ac-e8fba491e479
author: rothja
ms.author: jroth
ms.openlocfilehash: 3daad53087c876af8dc46bccc9c4bf7952976067
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87734054"
---
# <a name="issabortabort-ole-db"></a><span data-ttu-id="16d8e-102">ISSAbort::Abort (OLE DB)</span><span class="sxs-lookup"><span data-stu-id="16d8e-102">ISSAbort::Abort (OLE DB)</span></span>
  <span data-ttu-id="16d8e-103">Отменяет текущий набор строк и любые пакетные команды, ассоциированные с текущей командой.</span><span class="sxs-lookup"><span data-stu-id="16d8e-103">Cancels the current rowset plus any batched commands associated with the current command.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="16d8e-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="16d8e-104">Syntax</span></span>  
  
```  
  
HRESULT Abort(void);  
```  
  
## <a name="remarks"></a><span data-ttu-id="16d8e-105">Remarks</span><span class="sxs-lookup"><span data-stu-id="16d8e-105">Remarks</span></span>  
 <span data-ttu-id="16d8e-106">Если команда, выполнение которой прерывается, принадлежит хранимой процедуре, выполнение этой хранимой процедуры (и любых вызвавших ее процедур, а также командного пакета, из которого производился вызов процедуры) будет прервано.</span><span class="sxs-lookup"><span data-stu-id="16d8e-106">If the command being aborted is in a stored procedure, execution of the stored procedure (and any procedures which had called that procedure) will be terminated as well as the command batch which contains the stored procedure call.</span></span> <span data-ttu-id="16d8e-107">Если сервер в это время передавал клиенту результирующий набор, эта передача будет прекращена.</span><span class="sxs-lookup"><span data-stu-id="16d8e-107">If the server is in the process of transferring a result set to the client, this will be stopped.</span></span> <span data-ttu-id="16d8e-108">Если клиент не хочет получать результирующий набор, перед освобождением набора строк можно вызвать метод **ISSAbort::Abort** ; это ускорит высвобождение набора строк, но если в это время существует открытая транзакция и ее свойство XACT_ABORT имеет значение ON, при вызове **ISSAbort::Abort** произойдет откат транзакции.</span><span class="sxs-lookup"><span data-stu-id="16d8e-108">If the client does not want to consume a result set, calling **ISSAbort::Abort** before releasing the rowset will speed up the rowset release, but if there is an open transaction and XACT_ABORT is ON, the transaction will be rolled back when **ISSAbort::Abort** is called</span></span>  
  
 <span data-ttu-id="16d8e-109">После того как метод **ISSAbort::Abort** вернет результат S_OK, связанный с ним интерфейс **IMultipleResults** становится непригодным к использованию и вплоть до освобождения в ответ на любые вызовы методов возвращает результат DB_E_CANCELED (кроме методов, определенных для интерфейса **IUnknown** ).</span><span class="sxs-lookup"><span data-stu-id="16d8e-109">After **ISSAbort::Abort** returns S_OK, the associated **IMultipleResults** interface enters a unusable state and returns DB_E_CANCELED to all method calls (except for methods defined by the **IUnknown** interface) until it is released.</span></span> <span data-ttu-id="16d8e-110">Если из интерфейса **IMultipleResults** до вызова метода **Abort** был получен интерфейс **IRowset**, он также входит в непригодное к использованию состояние и в ответ на любые вызовы методов возвращает результат DB_E_CANCELED (кроме методов, определенных для интерфейсов **IUnknown** и **IRowset::ReleaseRows**), пока не будет освобожден успешным вызовом метода **ISSAbort::Abort**.</span><span class="sxs-lookup"><span data-stu-id="16d8e-110">If an **IRowset** had been obtained from **IMultipleResults** prior to a call to **Abort**, it also enters an unusable state and returns DB_E_CANCELED to all method calls (except for methods defined by the **IUnknown** interface and **IRowset::ReleaseRows**) until it is released after a successful call to **ISSAbort::Abort**.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="16d8e-111">Начиная с версии [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)], если состояние сервера XACT_ABORT имеет значение ON, вызов метода **ISSAbort::Abort** при подключении к [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] прекращает все транзакции, явные и неявные, и совершает их откат.</span><span class="sxs-lookup"><span data-stu-id="16d8e-111">Beginning with [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)], if the server XACT_ABORT state is ON, executing **ISSAbort::Abort** will terminate and roll back any current implicit or explicit transaction when connected to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="16d8e-112">Более ранние версии [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] не прекратят текущих транзакций.</span><span class="sxs-lookup"><span data-stu-id="16d8e-112">Earlier versions of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] will not abort the current transaction.</span></span>  
  
## <a name="arguments"></a><span data-ttu-id="16d8e-113">Аргументы</span><span class="sxs-lookup"><span data-stu-id="16d8e-113">Arguments</span></span>  
 <span data-ttu-id="16d8e-114">Нет.</span><span class="sxs-lookup"><span data-stu-id="16d8e-114">None.</span></span>  
  
## <a name="return-code-values"></a><span data-ttu-id="16d8e-115">Значения кода возврата</span><span class="sxs-lookup"><span data-stu-id="16d8e-115">Return Code Values</span></span>  
 <span data-ttu-id="16d8e-116">S_OK</span><span class="sxs-lookup"><span data-stu-id="16d8e-116">S_OK</span></span>  
 <span data-ttu-id="16d8e-117">Метод **ISSAbort::Abort** возвращает значение S_OK, если было прервано выполнение программного пакета, и DB_E_CANTCANCEL в противном случае.</span><span class="sxs-lookup"><span data-stu-id="16d8e-117">The **ISSAbort::Abort** method returns S_OK if the batch was canceled and DB_E_CANTCANCEL otherwise.</span></span> <span data-ttu-id="16d8e-118">Если выполнение программного пакета уже было прервано ранее, возвращается DB_E_CANCELED.</span><span class="sxs-lookup"><span data-stu-id="16d8e-118">If the batch has already been canceled, DB_E_CANCELED is returned.</span></span>  
  
 <span data-ttu-id="16d8e-119">DB_E_CANCELED</span><span class="sxs-lookup"><span data-stu-id="16d8e-119">DB_E_CANCELED</span></span>  
 <span data-ttu-id="16d8e-120">Выполнение пакета уже было прервано.</span><span class="sxs-lookup"><span data-stu-id="16d8e-120">The batch has already been canceled.</span></span>  
  
 <span data-ttu-id="16d8e-121">DB_E_CANTCANCEL</span><span class="sxs-lookup"><span data-stu-id="16d8e-121">DB_E_CANTCANCEL</span></span>  
 <span data-ttu-id="16d8e-122">Выполнение пакета не было прервано.</span><span class="sxs-lookup"><span data-stu-id="16d8e-122">The batch was not canceled.</span></span>  
  
 <span data-ttu-id="16d8e-123">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="16d8e-123">E_FAIL</span></span>  
 <span data-ttu-id="16d8e-124">Произошла ошибка конкретного поставщика; для получения дополнительных сведений используйте интерфейс [ISQLServerErrorInfo](../../database-engine/dev-guide/isqlservererrorinfo-ole-db.md) .</span><span class="sxs-lookup"><span data-stu-id="16d8e-124">A provider specific error occurred; for detailed information, use the [ISQLServerErrorInfo](../../database-engine/dev-guide/isqlservererrorinfo-ole-db.md) interface.</span></span>  
  
 <span data-ttu-id="16d8e-125">E_UNEXPECTED</span><span class="sxs-lookup"><span data-stu-id="16d8e-125">E_UNEXPECTED</span></span>  
 <span data-ttu-id="16d8e-126">Непредвиденный вызов метода.</span><span class="sxs-lookup"><span data-stu-id="16d8e-126">The call to the method was unexpected.</span></span> <span data-ttu-id="16d8e-127">Например, объект находится в состоянии зомби, потому что метод **ISSAbort::Abort** уже был вызван.</span><span class="sxs-lookup"><span data-stu-id="16d8e-127">For example, the object is in a zombie state because **ISSAbort::Abort** has already been called.</span></span>  
  
 <span data-ttu-id="16d8e-128">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="16d8e-128">E_OUTOFMEMORY</span></span>  
 <span data-ttu-id="16d8e-129">Ошибка, связанная с нехваткой памяти.</span><span class="sxs-lookup"><span data-stu-id="16d8e-129">Out of memory error.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="16d8e-130">См. также:</span><span class="sxs-lookup"><span data-stu-id="16d8e-130">See Also</span></span>  
 [<span data-ttu-id="16d8e-131">ISSAbort &#40;OLE DB&#41;</span><span class="sxs-lookup"><span data-stu-id="16d8e-131">ISSAbort &#40;OLE DB&#41;</span></span>](../../database-engine/dev-guide/issabort-ole-db.md)  
  
  
