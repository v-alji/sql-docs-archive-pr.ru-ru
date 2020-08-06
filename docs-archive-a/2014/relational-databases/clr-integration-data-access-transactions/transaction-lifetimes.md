---
title: Время существования транзакции | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: clr
ms.topic: reference
helpviewer_keywords:
- lifetimes [SQL Server]
- Transact-SQL vs. managed code
ms.assetid: cb076fda-6488-4959-a6a4-7adaccf3f25c
author: rothja
ms.author: jroth
ms.openlocfilehash: 8c00050ee323cade7493d44c4c296ba4ce6811e0
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87751192"
---
# <a name="transaction-lifetimes"></a><span data-ttu-id="93c0a-102">Время существования транзакций</span><span class="sxs-lookup"><span data-stu-id="93c0a-102">Transaction Lifetimes</span></span>
  <span data-ttu-id="93c0a-103">Между транзакциями, запускаемыми из хранимых процедур [!INCLUDE[tsql](../../includes/tsql-md.md)] и из управляемого кода, имеется существенное различие: код CLR не может разбалансировать состояние транзакции при входе или выходе из вызывающей среды CLR.</span><span class="sxs-lookup"><span data-stu-id="93c0a-103">There is an important difference between transactions started in [!INCLUDE[tsql](../../includes/tsql-md.md)] stored procedures and those started in managed code: common language runtime (CLR) code cannot unbalance the transaction state on entry or exit of a CLR invocation.</span></span> <span data-ttu-id="93c0a-104">Необходимо учитывать следующие последствия этого факта.</span><span class="sxs-lookup"><span data-stu-id="93c0a-104">Be aware of the following implications of this difference:</span></span>  
  
-   <span data-ttu-id="93c0a-105">Транзакцию, запущенную в среде CLR, необходимо зафиксировать или выполнить ее откат, иначе [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] сформирует ошибку при выходе из среды.</span><span class="sxs-lookup"><span data-stu-id="93c0a-105">A transaction started inside a CLR frame must be committed or rolled back, or else [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] generates an error when the frame is exited.</span></span>  
  
-   <span data-ttu-id="93c0a-106">Внешнюю транзакцию нельзя зафиксировать или выполнить ее откат внутри кода CLR.</span><span class="sxs-lookup"><span data-stu-id="93c0a-106">An outer transaction cannot be committed or rolled back inside the CLR code.</span></span>  
  
-   <span data-ttu-id="93c0a-107">Попытка зафиксировать транзакцию, запущенную в другой процедуре, вызывает ошибку времени выполнения.</span><span class="sxs-lookup"><span data-stu-id="93c0a-107">An attempt to commit a transaction not started in the same procedure causes a run-time error.</span></span>  
  
-   <span data-ttu-id="93c0a-108">Попытка отката транзакции, которая не была запущена в той же процедуре, приводит к тому, что транзакция перестает отвечать на запросы (что препятствует выполнению других побочных операций).</span><span class="sxs-lookup"><span data-stu-id="93c0a-108">An attempt to roll back a transaction not started in the same procedure causes the transaction to stop responding (preventing any other side-effecting operation from happening).</span></span> <span data-ttu-id="93c0a-109">Выполнение транзакции прекращается, пока код CLR не выйдет из области действия.</span><span class="sxs-lookup"><span data-stu-id="93c0a-109">The transaction discontinues until the CLR code goes out of scope.</span></span> <span data-ttu-id="93c0a-110">Обратите внимание, что эта особенность может быть полезной при обнаружении ошибки в процедуре и необходимости убедиться, что работа транзакции полностью прекращена.</span><span class="sxs-lookup"><span data-stu-id="93c0a-110">Note that this can be useful when you detect an error inside your procedure and want to make sure the whole transaction terminates.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="93c0a-111">См. также:</span><span class="sxs-lookup"><span data-stu-id="93c0a-111">See Also</span></span>  
 [<span data-ttu-id="93c0a-112">Интеграция со средой CLR и транзакции</span><span class="sxs-lookup"><span data-stu-id="93c0a-112">CLR Integration and Transactions</span></span>](../native-client-ole-db-transactions/transactions.md)  
  
  
