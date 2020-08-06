---
title: Интеграция со средой CLR и транзакции | Документация Майкрософт
ms.custom: ''
ms.date: 03/08/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: clr
ms.topic: reference
helpviewer_keywords:
- ADO.NET [CLR integration]
- common language runtime [SQL Server], ADO.NET
- managed code [SQL Server], transactions
- common language runtime [SQL Server], transactions
- System.Transactions namespace
- transactions [CLR integration]
ms.assetid: 381d206e-06e2-48d0-8206-295fcf06ac98
author: rothja
ms.author: jroth
ms.openlocfilehash: de72a2113aeb568decbdc9b5ee0174160cc0d3ef
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87751199"
---
# <a name="clr-integration-and-transactions"></a><span data-ttu-id="f21bf-102">Интеграция со средой CLR и транзакции</span><span class="sxs-lookup"><span data-stu-id="f21bf-102">CLR Integration and Transactions</span></span>
  <span data-ttu-id="f21bf-103">Пространство имен `System.Transactions` предоставляет новую платформу транзакций, полностью интегрированную с ADO.NET и со средой CLR [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f21bf-103">The `System.Transactions` namespace provides a transaction framework that is fully integrated with ADO.NET and [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] common language runtime (CLR) integration.</span></span> <span data-ttu-id="f21bf-104">Совместное использование пространства имен `System.Transactions` и ADO.NET позволяет расширить и упростить использование локальных и распределенных транзакций в управляемых приложениях.</span><span class="sxs-lookup"><span data-stu-id="f21bf-104">`System.Transactions` and ADO.NET work together to extend and simplify the use of local and distributed transactions in managed applications.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="f21bf-105">Определяемая пользователем процедура (UDP) среды CLR не может устанавливать соединение с тем же сервером, на котором она запускается (соединение, замкнутое на себя), и выполнить прикрепление в той же транзакции.</span><span class="sxs-lookup"><span data-stu-id="f21bf-105">A CLR user-defined procedure (UDP) cannot establish a connection to the same server it is running on (a loopback connection) and enlist in the same transaction.</span></span> <span data-ttu-id="f21bf-106">Если предпринимается такая попытка, то попытка соединения будет заблокирована, а управление не будет передано обратно определяемой пользователем процедуре.</span><span class="sxs-lookup"><span data-stu-id="f21bf-106">If this is attempted, the connection attempt will be blocked and control will not be passed back to the UDP.</span></span> <span data-ttu-id="f21bf-107">Это приведет к ошибке времени ожидания (сообщение 1206) в определяемой пользователем процедуре.</span><span class="sxs-lookup"><span data-stu-id="f21bf-107">This will result in a timeout error (Msg 1206) on the UDP.</span></span>  
  
 <span data-ttu-id="f21bf-108">Дополнительные сведения о транзакциях и платформе .NET Framework см. в разделах «Выполнение транзакций» и «Использование транзакций» пакета SDK для платформы .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="f21bf-108">For more information about transactions and the .NET Framework, see "Performing Transactions" and "Leveraging Transactions" in the .NET Framework SDK.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="f21bf-109">в этом разделе</span><span class="sxs-lookup"><span data-stu-id="f21bf-109">In This Section</span></span>  
 [<span data-ttu-id="f21bf-110">Повышение транзакции</span><span class="sxs-lookup"><span data-stu-id="f21bf-110">Transaction Promotion</span></span>](transaction-promotion.md)  
 <span data-ttu-id="f21bf-111">Содержит описание возможности повысить уровень транзакции и использования этой функции.</span><span class="sxs-lookup"><span data-stu-id="f21bf-111">Describes the ability to promote transactions, and how to use this feature.</span></span>  
  
 [<span data-ttu-id="f21bf-112">Доступ к текущей транзакции</span><span class="sxs-lookup"><span data-stu-id="f21bf-112">Accessing the Current Transaction</span></span>](accessing-the-current-transaction.md)  
 <span data-ttu-id="f21bf-113">Содержит описание получения доступа к транзакции, которая выполняется в данный момент внутрипроцессно на [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f21bf-113">Describes how to access a transaction currently running in-process on [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
 [<span data-ttu-id="f21bf-114">Использование System.Transactions</span><span class="sxs-lookup"><span data-stu-id="f21bf-114">Using System.Transactions</span></span>](../native-client-ole-db-transactions/transactions.md)  
 <span data-ttu-id="f21bf-115">Содержит описание использования прикладного программного интерфейса (API) `System.Transactions` в управляемом приложении.</span><span class="sxs-lookup"><span data-stu-id="f21bf-115">Describes how to use the `System.Transactions` application programming interface (API) in your managed application.</span></span>  
  
 [<span data-ttu-id="f21bf-116">Время существования транзакций</span><span class="sxs-lookup"><span data-stu-id="f21bf-116">Transaction Lifetimes</span></span>](transaction-lifetimes.md)  
 <span data-ttu-id="f21bf-117">Содержит описание различий во времени существования между транзакциями, запущенными в хранимых процедурах [!INCLUDE[tsql](../../includes/tsql-md.md)], и транзакциями, запущенными в приложениях CLR.</span><span class="sxs-lookup"><span data-stu-id="f21bf-117">Describes the difference in lifetime between transactions started in [!INCLUDE[tsql](../../includes/tsql-md.md)] stored procedures and transactions started in CLR applications.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f21bf-118">См. также:</span><span class="sxs-lookup"><span data-stu-id="f21bf-118">See Also</span></span>  
 [<span data-ttu-id="f21bf-119">Доступ к данным из объектов среды CLR для работы с базами данных</span><span class="sxs-lookup"><span data-stu-id="f21bf-119">Data Access from CLR Database Objects</span></span>](../clr-integration/data-access/data-access-from-clr-database-objects.md)  
  
  
