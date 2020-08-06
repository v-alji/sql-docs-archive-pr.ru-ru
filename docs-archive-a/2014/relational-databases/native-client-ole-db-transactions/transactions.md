---
title: Транзакции | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- OLE DB, transactions
- transactions [OLE DB]
- SQL Server Native Client OLE DB provider, transactions
ms.assetid: 3b41e33a-c1ca-4b2a-9464-312b0ed3ca89
author: rothja
ms.author: jroth
ms.openlocfilehash: 1067820e80f9c7a4e1af2c8a14c85bc9dbfdd6aa
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87667041"
---
# <a name="transactions"></a><span data-ttu-id="cf357-102">Транзакции</span><span class="sxs-lookup"><span data-stu-id="cf357-102">Transactions</span></span>
  <span data-ttu-id="cf357-103">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]Поставщик OLE DB собственного клиента реализует поддержку локальных транзакций.</span><span class="sxs-lookup"><span data-stu-id="cf357-103">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider implements local transaction support.</span></span> <span data-ttu-id="cf357-104">Потребитель может использовать распределенные или координируемые транзакции с помощью координатора распределенных транзакций (Майкрософт) (MS DTC).</span><span class="sxs-lookup"><span data-stu-id="cf357-104">The consumer can use distributed or coordinated transactions by using Microsoft Distributed Transaction Coordinator (MS DTC).</span></span> <span data-ttu-id="cf357-105">Для потребителей, которым необходим контроль транзакций, охватывающий несколько сеансов, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] поставщик OLE DB собственного клиента может присоединить транзакции, инициированные и обслуживаемые MS DTC.</span><span class="sxs-lookup"><span data-stu-id="cf357-105">For consumers requiring transaction control that spans multiple sessions, the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider can join transactions initiated and maintained by MS DTC.</span></span>  
  
 <span data-ttu-id="cf357-106">По умолчанию [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] поставщик OLE DB собственного клиента использует режим автоматической фиксации транзакций, где каждое дискретное действие в сеансе потребителя состоит из полной транзакции с экземпляром [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="cf357-106">By default, the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider uses an autocommit transaction mode, where each discrete action on a consumer session comprises a complete transaction against an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="cf357-107">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]Режим автоматической фиксации поставщика собственного клиента OLE DB является локальным, и транзакции с автоматической фиксацией никогда не охватывают более одного сеанса.</span><span class="sxs-lookup"><span data-stu-id="cf357-107">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider autocommit mode is local, and autocommit transactions never span more than a single session.</span></span>  
  
 <span data-ttu-id="cf357-108">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]Поставщик OLE DB собственного клиента предоставляет интерфейс **ITransactionLocal** , позволяя потребителю явно и неявно запускать транзакции в одном соединении с экземпляром [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="cf357-108">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider exposes the **ITransactionLocal** interface, allowing the consumer to use explicitly and implicitly start transactions on a single connection to an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="cf357-109">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]Поставщик собственного клиента OLE DB не поддерживает вложенные локальные транзакции.</span><span class="sxs-lookup"><span data-stu-id="cf357-109">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider does not support nested local transactions.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="cf357-110">в этом разделе</span><span class="sxs-lookup"><span data-stu-id="cf357-110">In This Section</span></span>  
  
-   [<span data-ttu-id="cf357-111">Поддержка локальных транзакций</span><span class="sxs-lookup"><span data-stu-id="cf357-111">Supporting Local Transactions</span></span>](supporting-local-transactions.md)  
  
-   [<span data-ttu-id="cf357-112">Поддержка распределенных транзакций</span><span class="sxs-lookup"><span data-stu-id="cf357-112">Supporting Distributed Transactions</span></span>](supporting-distributed-transactions.md)  
  
-   [<span data-ttu-id="cf357-113">Уровни изоляции (OLE DB)</span><span class="sxs-lookup"><span data-stu-id="cf357-113">Isolation Levels &#40;OLE DB&#41;</span></span>](isolation-levels-ole-db.md)  
  
## <a name="see-also"></a><span data-ttu-id="cf357-114">См. также:</span><span class="sxs-lookup"><span data-stu-id="cf357-114">See Also</span></span>  
 [<span data-ttu-id="cf357-115">SQL Server Native Client (OLE DB)</span><span class="sxs-lookup"><span data-stu-id="cf357-115">SQL Server Native Client &#40;OLE DB&#41;</span></span>](../native-client/ole-db/sql-server-native-client-ole-db.md)  
  
  
