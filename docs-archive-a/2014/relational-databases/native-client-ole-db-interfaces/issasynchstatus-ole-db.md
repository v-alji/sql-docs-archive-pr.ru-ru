---
title: ISSAsynchStatus (OLE DB) | Документация Майкрософт
ms.custom: ''
ms.date: 06/14/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
api_name:
- ISSAsynchStatus (OLE DB)
topic_type:
- apiref
helpviewer_keywords:
- ISSAsynchStatus interface
ms.assetid: c643f09f-9ccc-4d8b-9243-3cde86c2bd46
author: rothja
ms.author: jroth
ms.openlocfilehash: 4489f9d1ad576d49d885842f6969f9b61065791c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87657754"
---
# <a name="issasynchstatus-ole-db"></a><span data-ttu-id="0f766-102">ISSAsynchStatus (OLE DB)</span><span class="sxs-lookup"><span data-stu-id="0f766-102">ISSAsynchStatus (OLE DB)</span></span>
  <span data-ttu-id="0f766-103">Интерфейс**ISSAsynchStatus** в [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] поддерживает асинхронные операции.</span><span class="sxs-lookup"><span data-stu-id="0f766-103">**ISSAsynchStatus** exposes support for [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] asynchronous operations.</span></span> <span data-ttu-id="0f766-104">Этот необязательный интерфейс наследует основной интерфейс OLE DB — **IDBAsynchStatus**.</span><span class="sxs-lookup"><span data-stu-id="0f766-104">This is an optional interface that inherits from the core OLE DB interface **IDBAsynchStatus**.</span></span> <span data-ttu-id="0f766-105">Помимо методов **Abort** и **GetStatus** , унаследованных от **IDBAsynchStatus**, **ISSAsynchStatus** предоставляет один новый метод, который используется для ожидания конца асинхронной операции или истечения назначенного времени.</span><span class="sxs-lookup"><span data-stu-id="0f766-105">In addition to the **Abort** and **GetStatus** methods inherited from **IDBAsynchStatus**, **ISSAsynchStatus** provides one new method that is used to wait until an asynchronous operation has completed or a time-out occurs.</span></span>  
  
|<span data-ttu-id="0f766-106">Метод</span><span class="sxs-lookup"><span data-stu-id="0f766-106">Method</span></span>|<span data-ttu-id="0f766-107">Описание</span><span class="sxs-lookup"><span data-stu-id="0f766-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="0f766-108">ISSAsynchStatus::Abort (OLE DB)</span><span class="sxs-lookup"><span data-stu-id="0f766-108">ISSAsynchStatus::Abort &#40;OLE DB&#41;</span></span>](issasynchstatus-abort-ole-db.md)|<span data-ttu-id="0f766-109">Отменяет операцию асинхронного выполнения.</span><span class="sxs-lookup"><span data-stu-id="0f766-109">Cancels an asynchronously executing operation.</span></span>|  
|[<span data-ttu-id="0f766-110">ISSAsynchStatus::Abort (OLE DB)</span><span class="sxs-lookup"><span data-stu-id="0f766-110">ISSAsynchStatus::GetStatus &#40;OLE DB&#41;</span></span>](issasynchstatus-getstatus-ole-db.md)|<span data-ttu-id="0f766-111">Возвращает состояние операции асинхронного выполнения.</span><span class="sxs-lookup"><span data-stu-id="0f766-111">Returns the status of an asynchronously executing operation.</span></span>|  
|[<span data-ttu-id="0f766-112">ISSAsynchStatus::WaitForAsynchCompletion (OLE DB)</span><span class="sxs-lookup"><span data-stu-id="0f766-112">ISSAsynchStatus::WaitForAsynchCompletion &#40;OLE DB&#41;</span></span>](issasynchstatus-waitforasynchcompletion-ole-db.md)|<span data-ttu-id="0f766-113">Ждет завершения синхронной операции или истечения назначенного времени.</span><span class="sxs-lookup"><span data-stu-id="0f766-113">Waits until the asynchronously executing operation is complete or a time-out occurs.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="0f766-114">Remarks</span><span class="sxs-lookup"><span data-stu-id="0f766-114">Remarks</span></span>  
 <span data-ttu-id="0f766-115">Реализация метода **ISSAsynchStatus::GetStatus** в интерфейсе **ISSAsynchStatus** аналогична методу **IDBAsynchStatus::GetStatus** , за одним исключением: если инициализация объекта источника данных прервана преждевременно, возвращается не DB_E_CANCELED, а E_UNEXPECTED (хотя **ISSAsynchStatus::WaitForAsynchCompletion** возвращает DB_E_CANCELED).</span><span class="sxs-lookup"><span data-stu-id="0f766-115">The **ISSAsynchStatus** implementation of the **ISSAsynchStatus::GetStatus** method is the same as the **IDBAsynchStatus::GetStatus** method except that if the initialization of a data source object is aborted, E_UNEXPECTED is returned rather than DB_E_CANCELED (although **ISSAsynchStatus::WaitForAsynchCompletion** returns DB_E_CANCELED).</span></span> <span data-ttu-id="0f766-116">Это происходит потому, что объект источника данных не остается в обычном состоянии, следующем за аварийным прерыванием операции, чтобы можно было предпринимать новые попытки инициализации.</span><span class="sxs-lookup"><span data-stu-id="0f766-116">This is because the data source object is not left in the usual state following an abort operation, so that further initialization operations may be attempted.</span></span>  
  
 <span data-ttu-id="0f766-117">Следующие методы поддерживают асинхронное выполнение в [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="0f766-117">The following methods support the use of asynchronous execution in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]:</span></span>  
  
-   <span data-ttu-id="0f766-118">**ICommand::Execute**</span><span class="sxs-lookup"><span data-stu-id="0f766-118">**ICommand::Execute**</span></span>  
  
-   <span data-ttu-id="0f766-119">**IOpenRowset::OpenRowset**</span><span class="sxs-lookup"><span data-stu-id="0f766-119">**IOpenRowset::OpenRowset**</span></span>  
  
-   <span data-ttu-id="0f766-120">**IMultipleResults::GetResult**</span><span class="sxs-lookup"><span data-stu-id="0f766-120">**IMultipleResults::GetResult**</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0f766-121">См. также:</span><span class="sxs-lookup"><span data-stu-id="0f766-121">See Also</span></span>  
 <span data-ttu-id="0f766-122">[Интерфейсы &#40;OLE DB&#41;](../../database-engine/dev-guide/interfaces-ole-db.md) </span><span class="sxs-lookup"><span data-stu-id="0f766-122">[Interfaces &#40;OLE DB&#41;](../../database-engine/dev-guide/interfaces-ole-db.md) </span></span>  
 [<span data-ttu-id="0f766-123">Выполнение асинхронных операций</span><span class="sxs-lookup"><span data-stu-id="0f766-123">Performing Asynchronous Operations</span></span>](../native-client/features/performing-asynchronous-operations.md)  
  
  
