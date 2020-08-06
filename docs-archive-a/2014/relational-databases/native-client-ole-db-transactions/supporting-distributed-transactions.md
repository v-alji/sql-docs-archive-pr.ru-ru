---
title: Поддержка распределенных транзакций | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- OLE DB, transactions
- distributed transactions [OLE DB]
- MS DTC
- transactions [OLE DB]
- SQL Server Native Client OLE DB provider, transactions
- ITransactionJoin interface
- MS DTC, about distributed transaction support
ms.assetid: d250b43b-9260-4ea4-90cc-57d9a2f67ea7
author: rothja
ms.author: jroth
ms.openlocfilehash: 5a30a44dc007852922aa71685728b26e5bb872c3
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87738246"
---
# <a name="supporting-distributed-transactions"></a><span data-ttu-id="62b68-102">Поддержка распределенных транзакций</span><span class="sxs-lookup"><span data-stu-id="62b68-102">Supporting Distributed Transactions</span></span>
  [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]<span data-ttu-id="62b68-103">Потребители поставщика OLE DB собственного клиента могут использовать метод **ITransactionJoin:: жоинтрансактион** для участия в распределенной транзакции, которая координируется Microsoft координатор распределенных транзакций (MS DTC).</span><span class="sxs-lookup"><span data-stu-id="62b68-103">Native Client OLE DB provider consumers can use the **ITransactionJoin::JoinTransaction** method to participate in a distributed transaction coordinated by Microsoft Distributed Transaction Coordinator (MS DTC).</span></span>  
  
 <span data-ttu-id="62b68-104">Службы MS DTC предоставляют доступ к COM-объектам, которые позволяют клиентам запускать и участвовать в координированных транзакциях через несколько соединений с различными хранилищами данных.</span><span class="sxs-lookup"><span data-stu-id="62b68-104">MS DTC exposes COM objects that allow clients to initiate and participate in coordinated transactions across multiple connections to a variety of data stores.</span></span> <span data-ttu-id="62b68-105">Чтобы инициировать транзакцию, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] потребитель поставщика OLE DB собственного клиента использует интерфейс MS DTC **ITransactionDispenser** .</span><span class="sxs-lookup"><span data-stu-id="62b68-105">To initiate a transaction, the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider consumer uses the MS DTC **ITransactionDispenser** interface.</span></span> <span data-ttu-id="62b68-106">Элемент **BeginTransaction** интерфейса **ITransactionDispenser** возвращает ссылку на объект распределенной транзакции.</span><span class="sxs-lookup"><span data-stu-id="62b68-106">The **BeginTransaction** member of **ITransactionDispenser** returns a reference on a distributed transaction object.</span></span> <span data-ttu-id="62b68-107">Эта ссылка передается в [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] собственный поставщик OLE DB клиента с помощью **жоинтрансактион**.</span><span class="sxs-lookup"><span data-stu-id="62b68-107">This reference is passed to the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider using **JoinTransaction**.</span></span>  
  
 <span data-ttu-id="62b68-108">Службы MS DTC поддерживают асинхронную фиксацию и прерывание распределенных транзакций.</span><span class="sxs-lookup"><span data-stu-id="62b68-108">MS DTC supports asynchronous commit and abort on distributed transactions.</span></span> <span data-ttu-id="62b68-109">Для уведомления о состоянии асинхронных транзакций потребитель реализует интерфейс **ITransactionOutcomeEvents** и подключает интерфейс к объекту транзакции MS DTC.</span><span class="sxs-lookup"><span data-stu-id="62b68-109">For notification on asynchronous transaction status, the consumer implements the **ITransactionOutcomeEvents** interface and connects the interface to an MS DTC transaction object.</span></span>  
  
 <span data-ttu-id="62b68-110">Для распределенных транзакций [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] поставщик собственного клиента OLE DB реализует параметры **ITransactionJoin:: жоинтрансактион** следующим образом.</span><span class="sxs-lookup"><span data-stu-id="62b68-110">For distributed transactions, the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider implements **ITransactionJoin::JoinTransaction** parameters as follows.</span></span>  
  
|<span data-ttu-id="62b68-111">Параметр</span><span class="sxs-lookup"><span data-stu-id="62b68-111">Parameter</span></span>|<span data-ttu-id="62b68-112">Описание</span><span class="sxs-lookup"><span data-stu-id="62b68-112">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="62b68-113">*punkTransactionCoord*</span><span class="sxs-lookup"><span data-stu-id="62b68-113">*punkTransactionCoord*</span></span>|<span data-ttu-id="62b68-114">Указатель на объект транзакции MS DTC.</span><span class="sxs-lookup"><span data-stu-id="62b68-114">A pointer to an MS DTC transaction object.</span></span>|  
|<span data-ttu-id="62b68-115">*IsoLevel*</span><span class="sxs-lookup"><span data-stu-id="62b68-115">*IsoLevel*</span></span>|<span data-ttu-id="62b68-116">Игнорируется [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] поставщиком собственного клиента OLE DB.</span><span class="sxs-lookup"><span data-stu-id="62b68-116">Ignored by the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider.</span></span> <span data-ttu-id="62b68-117">Уровень изоляции для транзакций, координируемых с использованием служб MS DTC, определяется, когда пользователь получает объект транзакции от координатора MS DTC.</span><span class="sxs-lookup"><span data-stu-id="62b68-117">The isolation level for MS DTC-coordinated transactions is determined when the consumer acquires a transaction object from MS DTC.</span></span>|  
|<span data-ttu-id="62b68-118">*IsoFlags*</span><span class="sxs-lookup"><span data-stu-id="62b68-118">*IsoFlags*</span></span>|<span data-ttu-id="62b68-119">Должно быть равно 0.</span><span class="sxs-lookup"><span data-stu-id="62b68-119">Must be 0.</span></span> <span data-ttu-id="62b68-120">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]Поставщик OLE DB собственного клиента возвращает XACT_E_NOISORETAIN, если потребитель указал любое другое значение.</span><span class="sxs-lookup"><span data-stu-id="62b68-120">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider returns XACT_E_NOISORETAIN if any other value is specified by the consumer.</span></span>|  
|<span data-ttu-id="62b68-121">*POtherOptions*</span><span class="sxs-lookup"><span data-stu-id="62b68-121">*POtherOptions*</span></span>|<span data-ttu-id="62b68-122">Если значение не равно NULL, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] поставщик OLE DB собственного клиента запрашивает объект параметров из интерфейса.</span><span class="sxs-lookup"><span data-stu-id="62b68-122">If not NULL, the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider requests the options object from the interface.</span></span> <span data-ttu-id="62b68-123">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]Поставщик OLE DB собственного клиента возвращает XACT_E_NOTIMEOUT, если элемент *ултимеаут* объекта параметров не равен нулю.</span><span class="sxs-lookup"><span data-stu-id="62b68-123">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider returns XACT_E_NOTIMEOUT if the options object's *ulTimeout* member is not zero.</span></span> <span data-ttu-id="62b68-124">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]Поставщик OLE DB собственного клиента игнорирует значение элемента *сздескриптион* .</span><span class="sxs-lookup"><span data-stu-id="62b68-124">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider ignores the value of the *szDescription* member.</span></span>|  
  
 <span data-ttu-id="62b68-125">В этом примере осуществляется координирование транзакции с использованием координатора MS DTC.</span><span class="sxs-lookup"><span data-stu-id="62b68-125">This example coordinates transaction by using MS DTC.</span></span>  
  
```  
// Interfaces used in the example.  
IDBCreateSession*       pIDBCreateSession   = NULL;  
ITransactionJoin*       pITransactionJoin   = NULL;  
IDBCreateCommand*       pIDBCreateCommand   = NULL;  
IRowset*                pIRowset            = NULL;  
  
// Transaction dispenser and transaction from MS DTC.  
ITransactionDispenser*  pITransactionDispenser = NULL;  
ITransaction*           pITransaction       = NULL;  
  
    HRESULT             hr;  
  
// Get the command creation interface for the session.  
if (FAILED(hr = pIDBCreateSession->CreateSession(NULL,  
     IID_IDBCreateCommand, (IUnknown**) &pIDBCreateCommand)))  
    {  
    // Process error from session creation. Release any references and  
    // return.  
    }  
  
// Get a transaction dispenser object from MS DTC and  
// start a transaction.  
if (FAILED(hr = DtcGetTransactionManager(NULL, NULL,  
    IID_ITransactionDispenser, 0, 0, NULL,  
    (void**) &pITransactionDispenser)))  
    {  
    // Process error message from MS DTC, release any references,  
    // and then return.  
    }  
if (FAILED(hr = pITransactionDispenser->BeginTransaction(  
    NULL, ISOLATIONLEVEL_READCOMMITTED, ISOFLAG_RETAIN_DONTCARE,  
    NULL, &pITransaction)))  
    {  
    // Process error message from MS DTC, release any references,  
    // and then return.  
    }  
  
// Join the transaction.  
if (FAILED(pIDBCreateCommand->QueryInterface(IID_ITransactionJoin,  
    (void**) &pITransactionJoin)))  
    {  
    // Process failure to get an interface, release any references, and  
    // then return.  
    }  
if (FAILED(pITransactionJoin->JoinTransaction(  
    (IUnknown*) pITransaction, 0, 0, NULL)))  
    {  
    // Process join failure, release any references, and then return.  
    }  
  
// Get data into a rowset, then update the data. Functions are not  
// illustrated in this example.  
if (FAILED(hr = ExecuteCommand(pIDBCreateCommand, &pIRowset)))  
    {  
    // Release any references and return.  
    }  
  
// If rowset data update fails, then terminate the transaction, else  
// commit. The example doesn't retain the rowset.  
if (FAILED(hr = UpdateDataInRowset(pIRowset, bDelayedUpdate)))  
    {  
    // Get error from update, then abort.  
    pITransaction->Abort(NULL, FALSE, FALSE);  
    }  
else  
    {  
    if (FAILED(hr = pITransaction->Commit(FALSE, 0, 0)))  
        {  
        // Get error from failed commit.  
        //  
        // If a distributed commit fails, application logic could  
        // analyze failure and retry. In this example, terminate. The   
        // consumer must resolve this somehow.  
        pITransaction->Abort(NULL, FALSE, FALSE);  
        }  
    }  
  
if (FAILED(hr))  
    {  
    // Update of data or commit failed. Release any references and  
    // return.  
    }  
  
// Un-enlist from the distributed transaction by setting   
// the transaction object pointer to NULL.  
if (FAILED(pITransactionJoin->JoinTransaction(  
    (IUnknown*) NULL, 0, 0, NULL)))  
    {  
    // Process failure, and then return.  
    }  
  
// Release any references and continue.  
```  
  
## <a name="see-also"></a><span data-ttu-id="62b68-126">См. также:</span><span class="sxs-lookup"><span data-stu-id="62b68-126">See Also</span></span>  
 [<span data-ttu-id="62b68-127">Транзакции</span><span class="sxs-lookup"><span data-stu-id="62b68-127">Transactions</span></span>](transactions.md)  
  
  
