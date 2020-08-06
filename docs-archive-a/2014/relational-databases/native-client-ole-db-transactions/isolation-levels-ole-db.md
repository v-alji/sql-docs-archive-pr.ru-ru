---
title: Уровни изоляции (OLE DB) | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- OLE DB, transactions
- isolation levels [OLE DB]
- transactions [OLE DB]
- SQL Server Native Client OLE DB provider, transactions
ms.assetid: d70ee72c-6e2a-4bcd-9456-4a697a866361
author: rothja
ms.author: jroth
ms.openlocfilehash: c7f6cbff4e68eaedd3e78a82cddd872ba5f8f19e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87665298"
---
# <a name="isolation-levels-ole-db"></a><span data-ttu-id="b82a5-102">Уровни изоляции (OLE DB)</span><span class="sxs-lookup"><span data-stu-id="b82a5-102">Isolation Levels (OLE DB)</span></span>
  <span data-ttu-id="b82a5-103">Клиенты [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] могут управлять уровнями изоляции транзакций для соединения.</span><span class="sxs-lookup"><span data-stu-id="b82a5-103">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] clients can control transaction-isolation levels for a connection.</span></span> <span data-ttu-id="b82a5-104">Чтобы управлять уровнем изоляции транзакций, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] потребитель поставщика OLE DB собственного клиента использует:</span><span class="sxs-lookup"><span data-stu-id="b82a5-104">To control transaction-isolation level, the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider consumer uses:</span></span>  
  
-   <span data-ttu-id="b82a5-105">DBPROPSET_SESSION DBPROP_SESS_AUTOCOMMITISOLEVELS свойства для [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] режима автоматической фиксации по умолчанию для поставщика собственного клиента OLE DB.</span><span class="sxs-lookup"><span data-stu-id="b82a5-105">DBPROPSET_SESSION property DBPROP_SESS_AUTOCOMMITISOLEVELS for the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider default autocommit mode.</span></span>  
  
     <span data-ttu-id="b82a5-106">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]Поставщик OLE DB собственного клиента для уровня по умолчанию имеет значение DBPROPVAL_TI_READCOMMITTED.</span><span class="sxs-lookup"><span data-stu-id="b82a5-106">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider default for the level is DBPROPVAL_TI_READCOMMITTED.</span></span>  
  
-   <span data-ttu-id="b82a5-107">Параметр *isoLevel* метода **ITransactionLocal::StartTransaction** для локальных транзакций с ручной фиксацией.</span><span class="sxs-lookup"><span data-stu-id="b82a5-107">The *isoLevel* parameter of the **ITransactionLocal::StartTransaction** method for local manual-commit transactions.</span></span>  
  
-   <span data-ttu-id="b82a5-108">Параметр *isoLevel* метода **ITransactionDispenser::BeginTransaction** для распределенных транзакций с координацией MS DTC.</span><span class="sxs-lookup"><span data-stu-id="b82a5-108">The *isoLevel* parameter of the **ITransactionDispenser::BeginTransaction** method for MS DTC-coordinated distributed transactions.</span></span>  
  
 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="b82a5-109">разрешает доступ только для чтения на уровне изоляции чтения «грязных» данных.</span><span class="sxs-lookup"><span data-stu-id="b82a5-109">allows read-only access at the dirty read isolation level.</span></span> <span data-ttu-id="b82a5-110">Все другие уровни ограничивают параллелизм применением блокировок к объектам [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b82a5-110">All other levels restrict concurrency by applying locks to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] objects.</span></span> <span data-ttu-id="b82a5-111">Если клиент требует более высоких уровней параллелизма, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] применяет более строгие ограничения на параллельные обращения к данным.</span><span class="sxs-lookup"><span data-stu-id="b82a5-111">As the client requires greater concurrency levels, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] applies greater restrictions on concurrent access to data.</span></span> <span data-ttu-id="b82a5-112">Чтобы обеспечить максимальный уровень одновременного доступа к данным, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] потребитель поставщика OLE DB собственного клиента должен управлять своими запросами для конкретных уровней параллелизма.</span><span class="sxs-lookup"><span data-stu-id="b82a5-112">To maintain the highest level of concurrent access to data, the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider consumer should intelligently control its requests for specific concurrency levels.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="b82a5-113">В [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] появился уровень изоляции моментального снимка.</span><span class="sxs-lookup"><span data-stu-id="b82a5-113">[!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] introduced snapshot isolation level.</span></span> <span data-ttu-id="b82a5-114">Дополнительные сведения см. в разделе [Working with Snapshot Isolation](../native-client/features/working-with-snapshot-isolation.md).</span><span class="sxs-lookup"><span data-stu-id="b82a5-114">For more information, see [Working with Snapshot Isolation](../native-client/features/working-with-snapshot-isolation.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b82a5-115">См. также:</span><span class="sxs-lookup"><span data-stu-id="b82a5-115">See Also</span></span>  
 [<span data-ttu-id="b82a5-116">Транзакции</span><span class="sxs-lookup"><span data-stu-id="b82a5-116">Transactions</span></span>](transactions.md)  
  
  
