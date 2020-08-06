---
title: Место на диске журнала транзакций для операций обработки индекса | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: table-view-index
ms.topic: conceptual
helpviewer_keywords:
- index disk space [SQL Server]
- space [SQL Server], indexes
- transaction logs [SQL Server], disk space
- disk space [SQL Server], transaction logs
- space [SQL Server], transaction logs
ms.assetid: 4f8a4922-4507-4072-be67-c690528d5c3b
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: c34c9ff7a9494496d6c60d5920184c0ce86131d4
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87739914"
---
# <a name="transaction-log-disk-space-for-index-operations"></a><span data-ttu-id="8772c-102">Место на диске журнала транзакций для операций обработки индекса</span><span class="sxs-lookup"><span data-stu-id="8772c-102">Transaction Log Disk Space for Index Operations</span></span>
  <span data-ttu-id="8772c-103">При крупномасштабных операциях обработки индекса могут формироваться большие объемы загружаемых данных, что может привести к быстрому заполнению журнала транзакций.</span><span class="sxs-lookup"><span data-stu-id="8772c-103">Large-scale index operations can generate large data loads that can cause the transaction log to fill quickly.</span></span> <span data-ttu-id="8772c-104">Чтобы обеспечить возможность отката операции обработки индекса, журнал транзакций не может быть усечен до тех пор, пока операция обработки индекса не завершится; однако во время обработки индекса возможно выполнение резервного копирования журнала.</span><span class="sxs-lookup"><span data-stu-id="8772c-104">To make sure that the index operation can be rolled back, the transaction log cannot be truncated until the index operation has completed; however, the log can be backed up during the index operation.</span></span> <span data-ttu-id="8772c-105">Следовательно, журнал транзакций должен иметь достаточно места для хранения как транзакций обработки индекса, так и любых параллельных пользовательских транзакций, выполняющихся во время обработки индекса.</span><span class="sxs-lookup"><span data-stu-id="8772c-105">Therefore, the transaction log must have sufficient room to store both the index operation transactions and any concurrent user transactions for the duration of the index operation.</span></span> <span data-ttu-id="8772c-106">Это верно для операций обработки индекса как в режиме вне сети, так и в режиме в сети.</span><span class="sxs-lookup"><span data-stu-id="8772c-106">This is true for both offline and online index operations.</span></span> <span data-ttu-id="8772c-107">Так как доступ к базовым таблицам во время обработки индекса в режиме вне  сети невозможен, количество пользовательских транзакций может быть небольшим и заполнение журнала не будет таким стремительным.</span><span class="sxs-lookup"><span data-stu-id="8772c-107">Because the underlying tables cannot be accessed during an offline index operation, there may be few user transactions and the log may not grow as quickly.</span></span> <span data-ttu-id="8772c-108">Операции обработки индекса в режиме в сети не препятствуют пользовательской работе, поэтому обработка больших индексов вкупе с большим количеством параллельных пользовательских транзакций может привести к непрерывному заполнению журнала транзакций без возможности его усечения.</span><span class="sxs-lookup"><span data-stu-id="8772c-108">Online index operations do not prevent concurrent user activity, therefore, large-scale online index operations combined with significant concurrent user transactions can cause continuous growth of the transaction log without an option to truncate the log.</span></span>  
  
## <a name="recommendations"></a><span data-ttu-id="8772c-109">Рекомендации</span><span class="sxs-lookup"><span data-stu-id="8772c-109">Recommendations</span></span>  
 <span data-ttu-id="8772c-110">При крупномасштабных операциях обработки индекса следует принять во внимание следующие рекомендации:</span><span class="sxs-lookup"><span data-stu-id="8772c-110">When you run large-scale index operations, consider the following recommendations:</span></span>  
  
1.  <span data-ttu-id="8772c-111">Перед тем как выполнять крупномасштабную обработку индекса в сети, убедитесь в том что журнал транзакций зарезервирован и усечен, а также что в журнале достаточно места для хранения проектируемого индекса и пользовательских транзакций.</span><span class="sxs-lookup"><span data-stu-id="8772c-111">Make sure the transaction log has been backed up and truncated before running large-scale index operations online, and that the log has sufficient space to store the projected index and user transactions.</span></span>  
  
2.  <span data-ttu-id="8772c-112">Рассмотрите возможность установки параметра SORT_IN_TEMPDB в положение ON для операции обработки индекса.</span><span class="sxs-lookup"><span data-stu-id="8772c-112">Consider setting the SORT_IN_TEMPDB option to ON for the index operation.</span></span> <span data-ttu-id="8772c-113">Это отделяет транзакции индекса от параллельных пользовательских транзакций.</span><span class="sxs-lookup"><span data-stu-id="8772c-113">This separates the index transactions from the concurrent user transactions.</span></span> <span data-ttu-id="8772c-114">Транзакции индекса будут храниться в журнале транзакций **tempdb** , а параллельные пользовательские транзакции — в журнале транзакций пользовательской базы данных.</span><span class="sxs-lookup"><span data-stu-id="8772c-114">The index transactions will be stored in the **tempdb** transaction log, and the concurrent user transactions will be stored in the transaction log of the user database.</span></span> <span data-ttu-id="8772c-115">Это позволяет при необходимости выполнить усечение журнала транзакций пользовательской базы данных во время обработки индекса.</span><span class="sxs-lookup"><span data-stu-id="8772c-115">This allows for the transaction log of the user database to be truncated during the index operation if it is required.</span></span> <span data-ttu-id="8772c-116">Кроме того, если журнал **tempdb** находится не на одном с журналом пользовательской базы данных диске, два журнала не конкурируют в использовании одного места на диске.</span><span class="sxs-lookup"><span data-stu-id="8772c-116">Additionally, if the **tempdb** log is not on the same disk as the user database log, the two logs are not competing for the same disk space.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="8772c-117">Убедитесь том, что база данных и журнал транзакций **tempdb** имеют достаточно места на диске для выполнения обработки индекса.</span><span class="sxs-lookup"><span data-stu-id="8772c-117">Verify that the **tempdb** database and transaction log have sufficient disk space to handle the index operation.</span></span> <span data-ttu-id="8772c-118">Журнал транзакций **tempdb** не может быть усечен до тех пор, пока не завершится обработка индекса.</span><span class="sxs-lookup"><span data-stu-id="8772c-118">The **tempdb** transaction log cannot be truncated until the index operation is completed.</span></span>  
  
3.  <span data-ttu-id="8772c-119">Используйте модель восстановления базы данных, обеспечивающую минимальное число записей для операции обработки индекса.</span><span class="sxs-lookup"><span data-stu-id="8772c-119">Use a database recovery model that allows for minimal logging of the index operation.</span></span> <span data-ttu-id="8772c-120">Это позволит уменьшить размер журнала и предотвратить заполнение пространства журнала.</span><span class="sxs-lookup"><span data-stu-id="8772c-120">This may reduce the size of the log and prevent the log from filling the log space.</span></span>  
  
4.  <span data-ttu-id="8772c-121">Не выполняйте обработку индекса в сети в явной транзакции.</span><span class="sxs-lookup"><span data-stu-id="8772c-121">Do not run the online index operation in an explicit transaction.</span></span> <span data-ttu-id="8772c-122">Усечение журнала нельзя будет выполнить до завершения явной транзакции.</span><span class="sxs-lookup"><span data-stu-id="8772c-122">The log will not be truncated until the explicit transaction ends.</span></span>  
  
## <a name="related-content"></a><span data-ttu-id="8772c-123">См. также</span><span class="sxs-lookup"><span data-stu-id="8772c-123">Related Content</span></span>  
 [<span data-ttu-id="8772c-124">Disk Space Requirements for Index DDL Operations</span><span class="sxs-lookup"><span data-stu-id="8772c-124">Disk Space Requirements for Index DDL Operations</span></span>](disk-space-requirements-for-index-ddl-operations.md)  
  
 [<span data-ttu-id="8772c-125">Пример использования места на диске для индекса</span><span class="sxs-lookup"><span data-stu-id="8772c-125">Index Disk Space Example</span></span>](index-disk-space-example.md)  
  
  
